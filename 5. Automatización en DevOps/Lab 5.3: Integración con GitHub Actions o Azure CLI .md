# 🧪 Lab 5.3: Integración con GitHub Actions o Azure CLI

En este laboratorio aprenderás a extender tus pipelines de Azure DevOps usando **Azure CLI** para automatizar tareas de infraestructura, y a complementar tu flujo usando **GitHub Actions** si tu repositorio está alojado en GitHub.

---

## 🎯 Objetivo

- Ejecutar comandos de Azure CLI desde un pipeline  
- Realizar una acción externa como crear un grupo de recursos o revisar el estado de una app  
- Entender cuándo conviene usar GitHub Actions y cómo integrarlas con Azure Pipelines

---

## ☁️ Parte 1: Ejecutar comandos Azure CLI desde el pipeline

1. Abre tu archivo `azure-pipelines.yml`  
2. Dentro del `stage: Deploy` (o en un job nuevo), agrega una tarea de tipo `AzureCLI@2`

```
task: AzureCLI@2  
inputs:  
  azureSubscription: 'SC-Azure-Dev'  
  scriptType: 'bash'  
  scriptLocation: 'inlineScript'  
  inlineScript: |  
    az group create --name rg-app-banca-dev --location eastus  
    az webapp show --name app-banca-dev --resource-group rg-app-banca-dev
```
> Asegúrate de tener una Service Connection configurada con permisos adecuados.

---

## 🧪 Parte 2: Casos comunes para Azure CLI en pipelines

- Crear recursos en tiempo real  
- Desplegar archivos ARM o Bicep  
- Consultar estados de servicios antes de hacer deploy  
- Automatizar rotación de secretos en Key Vault  
- Validar condiciones de infraestructura antes de liberar a producción

---

## 🧩 Parte 3: Integración con GitHub Actions (si tu repo está en GitHub)

1. En el repositorio `app-banca-movil` en GitHub, crea el archivo:  
`.github/workflows/build.yml`

2. Define un workflow simple:

```
name: Build and Notify  
on:  
  push:  
    branches: [ main ]

jobs:  
  build:  
    runs-on: ubuntu-latest  
    steps:  
      - uses: actions/checkout@v3  
      - name: Setup Node  
        uses: actions/setup-node@v3  
        with:  
          node-version: 18  
      - run: npm install  
      - run: npm run build  
      - name: Notify Azure DevOps  
        run: curl -X POST https://dev.azure.com/...
```

> Este último paso puede llamar a un webhook o actualizar un work item en Azure DevOps si lo necesitas.

---

## ✅ Buenas prácticas

- Usa Azure CLI para tareas específicas que no cubren las tareas nativas de DevOps  
- No dupliques lógica entre pipelines y GitHub Actions si no es necesario  
- Documenta claramente en qué parte del flujo se usa cada herramienta  
- Mantén tus tokens de autenticación en variables secretas, no en texto plano

---

## 📚 Recursos adicionales

- Azure CLI en Azure Pipelines: https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/deploy/azure-cli  
- GitHub Actions para Azure: https://github.com/Azure/actions  
- Azure Service Connections: https://learn.microsoft.com/en-us/azure/devops/pipelines/library/service-endpoints

