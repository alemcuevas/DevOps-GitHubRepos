# 🧪 Lab 6.4: Revisión y aprobación de Pull Requests

En este laboratorio aprenderás a crear y gestionar Pull Requests en Azure Repos, configurar revisiones obligatorias, resolver comentarios y asegurar que los cambios estén correctamente aprobados antes de integrarse en la rama principal.

---

## 🎯 Objetivo

- Crear un Pull Request desde una rama de feature  
- Configurar políticas de revisión y aprobación  
- Resolver comentarios y realizar cambios iterativos  

---

## 🛠️ Parte 1: Crear un Pull Request

1. Abre tu repositorio `app-banca-movil` en Azure DevOps  
2. Crea una nueva rama: `feature/agregar-validacion`  
3. Realiza un cambio menor (ej. editar README o archivo de configuración)  
4. Haz push a la rama y ve a la pestaña `Repos > Pull Requests`  
5. Haz clic en **New Pull Request** y configura:

- Source: `feature/agregar-validacion`  
- Target: `main`  
- Título: `Agrega validación de correo electrónico (AB#456)`  
- Agrega una descripción clara de lo que se modificó  
- Selecciona 1 o 2 revisores del equipo

---

## 🔍 Parte 2: Revisión y ciclo de comentarios

1. El revisor puede dejar comentarios por línea, archivo o generales  
2. Como autor del PR, responde o marca como resuelto cada comentario  
3. Si es necesario, realiza cambios adicionales en la rama  
4. El PR se actualizará automáticamente con cada push nuevo

> La política de la rama puede requerir que todos los comentarios estén resueltos antes del merge.

---

## ✅ Parte 3: Aprobar y completar el Pull Request

1. El revisor hace clic en **Approve**  
2. Si todos los requisitos están cumplidos (revisores, build exitoso, work item vinculado), se habilita el botón **Complete**  
3. Selecciona el tipo de merge (`Squash`, recomendado)  
4. Confirma la fusión del código

---

## 🧠 Buenas prácticas

- Crea PRs pequeños y enfocados en una sola funcionalidad  
- Usa títulos descriptivos con ID de work item (ej. `AB#456`)  
- Siempre responde a los comentarios de revisión  
- Nunca apruebes un PR sin revisarlo por completo  
- Documenta el propósito y el impacto del cambio en la descripción  
- Habilita reglas que bloqueen merge sin aprobación ni validación

---

## 📚 Recursos adicionales

- Pull Requests en Azure Repos: https://learn.microsoft.com/en-us/azure/devops/repos/git/pull-requests  
- Resolver comentarios: https://learn.microsoft.com/en-us/azure/devops/repos/git/comment-on-pull-requests  
- Revisión efectiva de código: https://learn.microsoft.com/en-us/azure/devops/repos/git/pull-request-guidance

