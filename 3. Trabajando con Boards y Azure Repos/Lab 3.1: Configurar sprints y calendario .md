# 🧪 Lab 3.1: Configurar Azure Boards para gestión ágil de tareas

En este laboratorio aprenderás a configurar **Azure Boards** dentro del proyecto `app-banca-movil` de la organización `core-banca-ti` para implementar una metodología ágil de trabajo basada en **Scrum** o **Kanban**.

---

## 🎯 Objetivo

- Definir el proceso ágil del equipo
- Crear un área de trabajo para tu aplicación
- Configurar el equipo y sus miembros
- Definir el calendario de sprints
- Personalizar el tablero para la gestión visual de tareas

---

## 🛠️ Parte 1: Definir el proceso de trabajo

1. Accede a [https://dev.azure.com](https://dev.azure.com)
2. Entra en la organización `core-banca-ti` y selecciona el proyecto `app-banca-movil`
3. Ve a `Project Settings` > `Overview`
4. Revisa el tipo de proceso activo:
   - **Agile**, **Scrum**, **CMMI**, o **Basic**
   - Para este laboratorio se recomienda usar el **proceso Agile**

> ✅ Recomendación: El proceso Agile es ideal si deseas trabajar con historias de usuario, tareas y bugs en un tablero visual.

---

## 👥 Parte 2: Configurar el equipo y áreas

1. Ve a `Project Settings` > `Teams`
2. Si no existe, crea un equipo llamado `Desarrollo App Banca`
3. Asigna miembros al equipo (puedes usar tu cuenta y otras de prueba)

4. Ve a `Project Settings` > `Project Configuration`
5. Define un **área** específica para el equipo:
   - `app-banca-movil\Desarrollo`
6. Asocia el área al equipo desde su configuración (`Boards > Team Configuration`)

> ✅ Consejo: Usa áreas para dividir el trabajo por producto, módulo o responsabilidad del equipo.

---

## 📅 Parte 3: Configurar sprints y calendario

1. Ve a `Project Settings` > `Boards` > `Project configuration`
2. Define la estructura de iteraciones (sprints):

   - `Sprint 1` – Fecha inicio: hoy | Fecha fin: +2 semanas
   - `Sprint 2` – Fecha inicio: +2 semanas | Fecha fin: +4 semanas
   - `Sprint 3` – Fecha inicio: +4 semanas | Fecha fin: +6 semanas

3. Regresa a `Boards > Sprints` y confirma que las iteraciones aparezcan en la vista del equipo

> ✅ Recomendación: Usa iteraciones regulares (quincenales o mensuales) para establecer ciclos de planificación y entrega.

---

## 📋 Parte 4: Personalizar el tablero

1. Ve a `Boards > Boards`
2. Verás el tablero Kanban del equipo con las columnas predeterminadas:

   - `New` → `Active` → `Resolved` → `Closed`

3. Haz clic en el ícono de engrane ⚙️ para personalizar columnas o estados
4. Puedes agregar columnas como:
   - `Ready for Dev`, `In QA`, `Ready for Release`

> ✅ Recomendación: Ajusta las columnas al flujo real de trabajo de tu equipo, pero no exageres en cantidad.

---

## 📚 Recursos adicionales

- [Introducción a Azure Boards](https://learn.microsoft.com/en-us/azure/devops/boards/get-started/what-is-azure-boards)
- [Configurar sprints y áreas](https://learn.microsoft.com/en-us/azure/devops/boards/sprints/set-iteration-paths)
- [Personalizar el tablero Kanban](https://learn.microsoft.com/en-us/azure/devops/boards/boards/customize-cards)

