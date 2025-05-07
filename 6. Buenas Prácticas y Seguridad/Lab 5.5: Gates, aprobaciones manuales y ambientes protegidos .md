# 🧪 Lab 5.5: Gates, aprobaciones manuales y ambientes protegidos

En este laboratorio agregarás controles de seguridad y validaciones al pipeline antes de permitir despliegues a entornos críticos. Usarás **ambientes** con **aprobaciones manuales** y **gates automáticos** para validar condiciones externas.

---

## 🎯 Objetivo

- Crear un ambiente protegido (`prod`)  
- Configurar aprobaciones manuales antes del despliegue  
- Agregar un gate que valide condiciones antes de continuar

---

## 🛠️ Parte 1: Crear el ambiente y configurarlo

1. Entra a Azure DevOps > `Pipelines > Environments`  
2. Haz clic en **New environment**  
   - Nombre: `prod`  
   - Tipo: Kubernetes, VM o vacío (elige vacío si no necesitas recursos asociados)  

3. Una vez creado, haz clic en `prod` > **Approvals and checks**  
4. Agrega una nueva aprobación:  
   - Tipo: Manual  
   - Aprobadores: tú u otro miembro del equipo  

---

## 🔄 Parte 2: Agregar un gate automático

1. En el mismo panel de `Approvals and checks`, haz clic en **+ Add check**  
2. Selecciona **Invoke REST API**  
   - URL: una API que devuelva 200 si todo está listo para producción (puede ser ficticia)  
   - Tiempo de espera: 5 min  
   - Reintentos: 2

> Esto simula la validación de una condición externa (ej. sistema de calidad, validación de negocio).

---

## 📄 Parte 3: Configurar el pipeline para usar el ambiente

En la etapa `Deploy-Prod` del archivo `azure-pipelines.yml`, usa:

environment:  
  name: 'prod'  
  resourceName: 'prod'

Asegúrate de que esta etapa tenga `dependsOn: Deploy-Dev`  
y se ejecute solo en la rama `main`:

condition: and(succeeded(), eq(variables['Build.SourceBranch'], 'refs/heads/main'))

---

## ✅ Buenas prácticas

- Usa `Environments` para agrupar configuraciones de seguridad, aprobaciones y gates  
- Documenta en la wiki del equipo los criterios de aprobación  
- Usa Webhooks, API REST o Key Vault como validaciones externas en gates  
- Mantén las aprobaciones limitadas a roles con responsabilidad operativa

---

## 📚 Recursos adicionales

- Environments: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/environments  
- Approvals and gates: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/approvals  
- REST API gates: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/gates

