# 🧪 Lab 4.2: Introducción a YAML pipelines con parámetros y stages

En este laboratorio extenderás tu pipeline YAML usando **parámetros reutilizables** y **etapas (stages)** para organizar el flujo en fases separadas como `Build` y `Test`. Esto mejorará la mantenibilidad, visibilidad y control del pipeline CI/CD.

---

## 🎯 Objetivo

- Reorganizar el pipeline usando `stages`
- Definir pasos separados para compilación y pruebas
- Introducir `parameters` para personalizar comportamientos del pipeline

---

## 🛠️ Parte 1: Agregar etapas (stages)

1. Abre el archivo `azure-pipelines.yml` en la raíz del repositorio `app-banca-movil`
2. Reemplaza el contenido del pipeline anterior por una versión dividida en stages

### Estructura sugerida:

- Stage: `Build`
  - Paso: `npm install`
  - Paso: `npm run build`

- Stage: `Test`
  - Depende de `Build`
  - Paso: `npm run test`

3. Cada etapa debe estar en su propio bloque `stage` con su respectivo `job` y `steps`

---

## ⚙️ Parte 2: Agregar parámetros

1. En la parte superior del YAML, declara un bloque `parameters`:

   - `runTests`: booleano (default: true)
   - `nodeVersion`: texto (default: '18.x')

2. Usa estos parámetros dentro de los `steps`:

   - NodeTool usará `nodeVersion`
   - El `stage: Test` se ejecutará solo si `runTests` es true

> ✅ Puedes definir los parámetros directamente o pasarlos desde Azure DevOps al lanzar el pipeline manualmente

---

## 📋 Ejemplo de uso

Cuando corras el pipeline manualmente desde Azure Pipelines:

1. Haz clic en **Run pipeline**
2. Se mostrarán los parámetros definidos:
   - Cambia `runTests` a `false` si deseas omitir pruebas
   - Cambia la versión de Node si lo necesitas

---

## 🔍 Parte 3: Validar el resultado

1. Asegúrate de que las etapas aparezcan como secciones separadas en la interfaz de ejecución
2. Verifica si se respetan las condiciones de ejecución basadas en los parámetros

---

## ✅ Buenas prácticas

- Usa `stages` para separar lógica de `build`, `test`, `deploy`
- Define parámetros configurables para aumentar la reutilización del pipeline
- Usa `condition:` para omitir etapas según valores de parámetros
- Documenta cada sección del YAML dentro del archivo con comentarios

---

## 📚 Recursos adicionales

- [Stages en Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/stages)
- [Uso de parámetros en YAML](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/templates#parameters)
- [Condiciones para ejecutar jobs y etapas](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/conditions)

