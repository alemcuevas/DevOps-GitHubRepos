# 🧪 Lab 4.3: Despliegue continuo (CD) a Azure App Service

En este laboratorio agregarás una etapa de **entrega continua (CD)** al pipeline para desplegar automáticamente tu aplicación a un **Azure App Service** cada vez que se cumplan ciertas condiciones.

---

## 🎯 Objetivo

- Conectar el pipeline a un Azure App Service
- Automatizar el despliegue desde la rama `main`
- Usar una Service Connection segura

---

## ✅ Requisitos previos

- Una instancia de **Azure App Service** ya creada (ejemplo: `app-banca-dev`)
- Una **Azure Service Connection** configurada en el proyecto (`SC-Azure-Dev`)

---

## 🛠️ Parte 1: Agregar la etapa de despliegue

1. Abre el archivo `azure-pipelines.yml` del repositorio `app-banca-movil`
2. Agrega una nueva `stage: Deploy` que se ejecute solo en la rama `main`

### La etapa debe incluir:

- Tarea `AzureWebApp@1` para desplegar
- Referencia a la `serviceConnectionName: SC-Azure-Dev`
- Parámetros como:
  - `appName: app-banca-dev`
  - `package`: ruta del artefacto (por ejemplo `$(System.DefaultWorkingDirectory)/build`)

3. Usa condición para ejecutar solo cuando:
   - `Build` y `Test` pasen
   - La rama sea `main`

---

## 🔄 Parte 2: Configurar el pipeline para múltiples entornos (opcional)

- Puedes agregar una variable de entorno:
  - `environmentName`: `dev`, `qa`, `prod`
- Condiciona la ejecución del `stage: Deploy` según el valor de esta variable
- Usa `dependsOn:` para asegurar que la etapa se ejecute después de `Build` y `Test`

---

## 🔍 Parte 3: Validar el despliegue

1. Haz un push a la rama `main`
2. Observa en Azure Pipelines la ejecución de las etapas
3. Una vez completado el `Deploy`, ve al portal de Azure:
   - Revisa que tu App Service esté actualizado
   - Verifica la versión desplegada (puedes usar una etiqueta o número de build)

---

## ✅ Buenas prácticas

- Usa diferentes App Services para cada ambiente (`dev`, `qa`, `prod`)
- Nunca uses credenciales directamente en YAML (usa Service Connections seguras)
- Asocia el despliegue a un `Environment` en Azure DevOps para habilitar aprobaciones y auditoría
- Usa nombres claros para stages y artefactos (`Deploy-AppService-Dev`, etc.)

---

## 📚 Recursos adicionales

- [Desplegar a Azure App Service](https://learn.microsoft.com/en-us/azure/devops/pipelines/ecosystems/javascript?tabs=yaml#deploy-your-app)
- [Tarea AzureWebApp@1](https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/deploy/azure-rm-web-app-deployment)
- [Usar ambientes en Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/environments)

