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

![image](https://github.com/user-attachments/assets/c22aab55-cb2b-4de7-8713-30ead0e0a2ac)

---

## 🔗 Parte 2: Vincular un commit a un work item

1. Abre tu repositorio `app-banca-movil` en GitHub
2. En una nueva rama (`feature/validacion-correo`), realiza un cambio relevante
3. Al hacer commit, usa la siguiente sintaxis en el mensaje:

   - `"Agrega validación de correo electrónico (AB#103)"`

![image](https://github.com/user-attachments/assets/56ea627a-8f8c-4b9a-a0ce-ffe417eeb3c9)
![image](https://github.com/user-attachments/assets/5817c0a0-9c24-4163-ba13-7a3f554bf255)

4. Haz push al repositorio y crea un **Pull Request** hacia `main` o `develop`

![image](https://github.com/user-attachments/assets/48e385d3-469d-4be2-a786-3a82d7c57c55)
![image](https://github.com/user-attachments/assets/f590dab1-828b-4571-a803-45d3845aa2ff)

> ✅ Azure DevOps detectará el identificador `AB#103` y enlazará automáticamente el cambio al work item correspondiente.

---

## 🔍 Parte 3: Visualiza el vínculo

1. Ve a `Boards > Work items`
2. Abre la historia `AB#103`
3. En la pestaña `Development` verás:
   - El commit vinculado desde GitHub
   - El pull request asociado (si fue creado)

![image](https://github.com/user-attachments/assets/7eef4d67-37bc-4b01-8276-fa8212da5d36)

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

