# 🧪 Lab 3.2: Crear work items y vincularlos a commits/pull requests en GitHub

En este laboratorio usarás **Azure Boards** para planificar tareas (work items) y aprenderás a **vincularlos con commits y pull requests** desde tu repositorio `app-banca-movil` en GitHub. Esto permitirá trazabilidad completa entre el código fuente y las tareas del proyecto.

---

## 🎯 Objetivo

- Crear tareas y bugs desde Azure Boards
- Asignar trabajo al equipo
- Vincular automáticamente commits y PRs al trabajo planificado
- Visualizar el progreso desde el tablero y cada work item

---

## 🛠️ Parte 1: Crear work items

1. Ve a [https://dev.azure.com](https://dev.azure.com)  
2. Abre tu proyecto `core-banca-ti > app-banca-movil`
3. Navega a `Boards > Work items`

4. Haz clic en **New Work Item** y selecciona **User Story**
   - Título: `Agregar validación de correo electrónico en login`
   - Asignado a: tu usuario
   - Área: `app-banca-movil\Desarrollo`
   - Iteración: `Sprint 1`

5. Guarda el work item y toma nota de su ID, por ejemplo: `AB#103`

---

## 🔗 Parte 2: Vincular un commit a un work item

1. Abre tu repositorio `app-banca-movil` en GitHub
2. En una nueva rama (`feature/validacion-correo`), realiza un cambio relevante
3. Al hacer commit, usa la siguiente sintaxis en el mensaje:

   - `"Agrega validación de correo electrónico (AB#103)"`

4. Haz push al repositorio y crea un **Pull Request** hacia `main` o `develop`

> ✅ Azure DevOps detectará el identificador `AB#103` y enlazará automáticamente el cambio al work item correspondiente.

---

## 🔍 Parte 3: Visualiza el vínculo

1. Ve a `Boards > Work items`
2. Abre la historia `AB#103`
3. En la pestaña `Development` verás:
   - El commit vinculado desde GitHub
   - El pull request asociado (si fue creado)

---

## ✅ Buenas prácticas

- Siempre vincula tus commits y PRs a un work item usando la sintaxis `AB#<ID>`
- No mezcles múltiples work items en un solo commit
- Evita vincular commits triviales (como cambios de formato o comentarios)
- Usa ramas por funcionalidad: `feature/`, `bugfix/`, etc.

---

## 📚 Recursos adicionales

- [GitHub commits to Azure Boards](https://learn.microsoft.com/en-us/azure/devops/boards/github/connect-to-github?view=azure-devops&tabs=browser#link-github-commits-and-pull-requests-to-work-items)
- [Trabajar con historias de usuario](https://learn.microsoft.com/en-us/azure/devops/boards/backlogs/manage-your-backlog)

