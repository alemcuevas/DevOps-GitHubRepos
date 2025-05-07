# 🧪 Lab 5.4: Uso de variables, plantillas y condiciones en pipelines avanzados

En este laboratorio usarás **variables personalizadas**, **plantillas reutilizables** y **condiciones** para controlar la ejecución dinámica de pasos, jobs y stages dentro de tus pipelines. Esto te dará mayor flexibilidad y facilitará la gestión de múltiples entornos.

---

## 🎯 Objetivo

- Declarar y utilizar variables en distintas partes del pipeline  
- Crear una plantilla reutilizable con parámetros  
- Aplicar condiciones para ejecutar tareas según el entorno o rama

---

## 📁 Parte 1: Crear una plantilla de tareas compartidas

1. Crea un archivo en la carpeta `templates/` llamado:  
   `steps-install-deps.yml`

2. Define una plantilla de pasos:

parameters:  
  nodeVersion: '18'  

steps:  
  - task: NodeTool@0  
    inputs:  
      versionSpec: ${{ parameters.nodeVersion }}  
  - script: npm install  
    displayName: 'Instalar dependencias'

---

## 🧾 Parte 2: Usar variables definidas

1. En la parte superior de tu archivo `azure-pipelines.yml`, agrega:

variables:  
  buildConfig: 'Release'  
  deployEnv: 'dev'  
  runTests: true

2. Usa estas variables en tus pasos:

- script: echo "Entorno de despliegue: $(deployEnv)"  
- condition: eq(variables['runTests'], true)

---

## 🧩 Parte 3: Llamar la plantilla desde el pipeline principal

- template: templates/steps-install-deps.yml  
  parameters:  
    nodeVersion: '18'

Coloca este bloque dentro del stage `Build`.

---

## 🔄 Parte 4: Aplicar condiciones en jobs y stages

Agrega condiciones para controlar el flujo según rama o variable:

condition: and(succeeded(), eq(variables['Build.SourceBranchName'], 'main'))

Otra opción más flexible:

condition: and(succeeded(), eq(variables['deployEnv'], 'prod'))

Esto permite que la etapa de despliegue solo se ejecute si la variable coincide con el entorno deseado.

---

## ✅ Buenas prácticas

- Usa plantillas para pasos repetitivos como build, lint, test o deploy  
- Define variables globales y por entorno en grupos o directamente en YAML  
- Usa condiciones claras para etapas críticas como producción  
- Documenta el propósito de cada variable y plantilla en comentarios YAML

---

## 📚 Recursos adicionales

- Plantillas YAML: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/templates  
- Variables en pipelines: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables  
- Condiciones en YAML: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/conditions

