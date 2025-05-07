# 🧪 Lab 4.1: Crear tu primer pipeline CI/CD desde GitHub

En este laboratorio configurarás tu primer pipeline de CI/CD desde Azure Pipelines conectado a tu repositorio `app-banca-movil` en GitHub. Automatizarás el proceso de instalación, pruebas y build para asegurar que tu aplicación sea validada con cada cambio.

---

## 🎯 Objetivo

- Crear un pipeline basado en YAML
- Ejecutar pasos automáticos de CI: instalación, pruebas y build
- Usar GitHub como repositorio fuente

---

## 🛠️ Parte 1: Crear el pipeline

1. Ingresa a [https://dev.azure.com](https://dev.azure.com)
2. Selecciona tu organización: `core-banca-ti`
3. Abre el proyecto: `app-banca-movil`
4. Navega a `Pipelines > Pipelines`
5. Haz clic en **New Pipeline**

![image](https://github.com/user-attachments/assets/bb4b71b9-3774-495d-8fec-9cce60113188)

---

### Configuración inicial

1. Selecciona `GitHub (YAML)`
2. Autoriza la conexión si aún no lo has hecho
3. Busca y selecciona tu repositorio: `alemcuevas/app-banca-movil`
4. Selecciona **Starter pipeline** o usa un archivo YAML existente

![image](https://github.com/user-attachments/assets/1e340056-50be-458f-b68b-c2f5d13446d9)

![image](https://github.com/user-attachments/assets/55ae5544-ce87-4ad5-9768-4736abbc1999)

![image](https://github.com/user-attachments/assets/3b157cd5-aa58-4f77-8b1f-c1d7875a2221)

---

## 🧾 Parte 2: Definir un pipeline básico

Agrega el siguiente contenido al archivo `azure-pipelines.yml`:

```bash

trigger:
  branches:
    include:
      - main

pool:
  vmImage: 'ubuntu-latest'

steps:
  - task: NodeTool@0
    inputs:
      versionSpec: '18.x'
    displayName: 'Instalar Node.js 18'

  - script: npm install
    displayName: 'Instalar dependencias'

  - script: npm run test
    displayName: 'Ejecutar pruebas'

  - script: npm run build
    displayName: 'Compilar aplicación'
```
![image](https://github.com/user-attachments/assets/67271381-62f7-49b1-94b9-6f86e904d6ef)

Guarda y confirma los cambios para que se guarden directamente en tu repositorio GitHub.

> ✅ Puedes editar directamente desde Azure o abrir el archivo en VSCode y subirlo manualmente.

---

## 🔍 Parte 3: Validar la ejecución

1. Regresa a `Pipelines` y selecciona el pipeline recién creado
2. Verifica que se haya ejecutado correctamente:
   - Debes ver los pasos ejecutados y sus logs
   - Si hay errores de lint o pruebas, el pipeline fallará

---

## ✅ Buenas prácticas

- Mantén el archivo YAML versionado en la raíz del repositorio
- Usa ramas para pruebas antes de modificar el pipeline en `main`
- Divide los pipelines en etapas (`build`, `test`, `deploy`) en futuros labs
- Usa comentarios claros dentro del YAML para explicar cada paso

---

## 📚 Recursos adicionales

- [Primer pipeline con GitHub y Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/create-first-pipeline)
- [Referencia de tareas YAML](https://learn.microsoft.com/en-us/azure/devops/pipelines/yaml-schema)
- [Ejemplo de pipelines Node.js](https://learn.microsoft.com/en-us/azure/devops/pipelines/ecosystems/javascript)

