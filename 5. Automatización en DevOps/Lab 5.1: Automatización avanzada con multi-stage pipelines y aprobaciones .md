# 🧪 Lab 5.1: Automatización avanzada con multi-stage pipelines y aprobaciones

En este laboratorio transformarás tu pipeline en un flujo multi-stage con validaciones y una **aprobación manual** antes de desplegar a producción. Aprenderás a dividir el pipeline en etapas, condicionar la ejecución y proteger entornos.

---

## 🎯 Objetivo

- Organizar el pipeline en múltiples etapas (`Build`, `Test`, `Deploy-Dev`, `Deploy-Prod`)
- Usar ambientes (`Environments`) para gestionar aprobaciones
- Forzar revisión humana antes del despliegue a producción

---

## 🧱 Parte 1: Estructura general del pipeline

1. Abre el archivo `azure-pipelines.yml`
2. Organiza el contenido en 4 stages:

- `Build`: instalar dependencias y compilar
- `Test`: ejecutar pruebas
- `Deploy-Dev`: despliegue automático sin aprobación
- `Deploy-Prod`: despliegue solo con aprobación

3. Usa `dependsOn` para encadenar etapas:

- `Test` depende de `Build`  
- `Deploy-Dev` depende de `Test`  
- `Deploy-Prod` depende de `Deploy-Dev`

---

## 🔐 Parte 2: Configurar entornos y aprobación

1. Ve a Azure DevOps > `Pipelines > Environments`
2. Crea dos entornos:
   - `dev`
   - `prod`

3. En el entorno `prod`:

- Agrega una aprobación manual (usuario o grupo que debe revisar)
- Opcional: agrega un `check` como validación de pipeline o revisión externa

4. En el YAML, usa la propiedad `environment:` en la etapa `Deploy-Prod`:

environment:  
  name: 'prod'  
  resourceName: 'prod'  
  environmentType: 'virtualMachine' (o 'deploymentGroup' o ninguno según tu caso)

> Si usas solo App Service, puedes omitir `resourceName`.

---

## ⚙️ Parte 3: Lógica del despliegue condicional

En la etapa `Deploy-Prod`, usa una condición que evalúe si estás en la rama `main`:

condition: and(succeeded(), eq(variables['Build.SourceBranch'], 'refs/heads/main'))

Esto asegura que el despliegue a producción solo ocurra con código aprobado y desde la rama principal.

---

## 🔍 Parte 4: Ejecutar y validar

1. Haz push a `main`
2. Observa la ejecución de stages en Azure Pipelines
3. La etapa `Deploy-Prod` se detendrá hasta recibir aprobación manual
4. Una vez aprobada, el despliegue continuará

---

## ✅ Buenas prácticas

- Define claramente los entornos (`dev`, `qa`, `staging`, `prod`)
- Asigna aprobadores por entorno y documenta criterios de aprobación
- Usa plantillas para separar la lógica de cada etapa
- Aplica `conditions` y `dependsOn` para tener control fino del flujo

---

## 📚 Recursos adicionales

- Multi-stage pipelines: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/stages  
- Environments y aprobaciones: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/environments  
- Conditions en YAML: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/conditions
