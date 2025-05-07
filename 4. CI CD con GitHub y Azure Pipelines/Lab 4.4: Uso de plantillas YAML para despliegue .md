# 🧪 Lab 4.4: Uso de plantillas YAML para despliegue

En este laboratorio separarás la lógica del despliegue en una plantilla externa para mejorar la organización y reutilización de tu pipeline. Esto es especialmente útil cuando se trabaja con múltiples entornos o aplicaciones similares.

---

## 🎯 Objetivo

- Crear una plantilla YAML de despliegue reutilizable  
- Llamar esa plantilla desde el pipeline principal  
- Definir parámetros en la plantilla para flexibilizar su uso

---

## 📁 Parte 1: Estructura del repositorio

1. En el repositorio `app-banca-movil`, crea una carpeta llamada:  
   `templates/`

2. Dentro de ella, crea un archivo llamado:  
   `deploy-appservice.yml`

---

## 🧱 Parte 2: Crear la plantilla de despliegue

En el archivo `templates/deploy-appservice.yml` define lo siguiente:

**Parámetros esperados:**

- `serviceConnection`
- `appName`
- `packagePath`
- `environmentName`

**Contenido básico de la plantilla:**

stage: Deploy  
  jobs:  
    - job: DeployApp  
      steps:  
        - task: AzureWebApp@1  
          inputs:  
            azureSubscription: $(serviceConnection)  
            appName: $(appName)  
            package: $(packagePath)

> Asegúrate de que los parámetros estén bien nombrados y referenciados con `$(...)` donde se usen dentro del YAML.

---

## 📄 Parte 3: Modificar el pipeline principal

1. Abre el archivo `azure-pipelines.yml` en la raíz del repositorio  
2. Reemplaza el bloque de la etapa `Deploy` por la llamada a la plantilla:

template: templates/deploy-appservice.yml  
parameters:  
  serviceConnection: 'SC-Azure-Dev'  
  appName: 'app-banca-dev'  
  packagePath: '$(System.DefaultWorkingDirectory)/build'  
  environmentName: 'dev'

---

## 🔍 Parte 4: Validar y ejecutar

1. Haz commit de los archivos modificados  
2. Ve a Azure DevOps > Pipelines  
3. Ejecuta manualmente el pipeline y verifica que:

- El template se carga correctamente  
- La etapa `Deploy` se ejecuta usando los parámetros definidos  

---

## ✅ Buenas prácticas

- Centraliza plantillas compartidas en una carpeta `templates/`
- Usa nombres descriptivos para cada archivo y parámetro
- Comenta dentro del YAML para explicar cada parámetro
- Versiona las plantillas igual que el código fuente

---

## 📚 Recursos adicionales

- Plantillas YAML: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/templates  
- Parámetros: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/templates#parameters  
- AzureWebApp@1: https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/deploy/azure-rm-web-app-deployment
