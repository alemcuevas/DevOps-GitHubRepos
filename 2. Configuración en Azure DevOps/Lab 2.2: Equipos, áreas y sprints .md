Parte 2: Configurar equipos, áreas y sprints en Azure DevOps

En esta segunda parte del laboratorio, estructurarás el proyecto `app-banca-movil` dentro de la organización `core-banca-ti`, creando equipos funcionales, dividiendo el trabajo en áreas y planificando iteraciones para una entrega ágil y organizada.

---

## 🎯 Objetivos

- Crear y configurar múltiples equipos dentro de un solo proyecto.
- Definir una jerarquía clara de áreas por módulo funcional.
- Crear y asignar iteraciones (sprints) para planificación ágil.
- Asignar a cada equipo su propia área e iteraciones.

---

## 🧠 Conceptos clave

### 👥 Equipos
Grupos funcionales dentro de un proyecto que permiten tener su propio backlog, tablero y métricas de sprint.

### 📂 Áreas
Representan módulos funcionales del sistema, permitiendo clasificar work items por dominio o componente.

### 🗓️ Iteraciones (Sprints)
Períodos definidos para planificar y ejecutar tareas, típicamente de 1 a 3 semanas.

---

## 🛠️ Pasos del laboratorio

### 1. Accede al proyecto

1. Abre [https://dev.azure.com](https://dev.azure.com)
2. Inicia sesión y selecciona la organización: `core-banca-ti`
3. Haz clic en el proyecto: `app-banca-movil`


---

### 2. Crear equipos funcionales

1. Ve a **Project Settings** > **Teams**.
2. Crea los siguientes equipos:

| Nombre del equipo       | Descripción                                             |
|-------------------------|----------------------------------------------------------|
| `frontend-app`          | Desarrollo de la interfaz móvil (Android y iOS)          |
| `backend-servicios`     | Implementación de servicios REST para operaciones bancarias |
| `qa-automatizacion`     | Diseño y ejecución de pruebas automáticas                |

3. Asegúrate de marcar la casilla **"Create area path"** al crear cada equipo.


---

### 3. Crear estructura de áreas

1. Ve a **Project Settings** > **Project configuration** > **Areas**.
2. Verifica o crea las siguientes rutas:

```bash
\app-banca-movil\frontend-app
\app-banca-movil\backend-servicios
\app-banca-movil\qa-automatizacion
```


### 3.1 Agrega subáreas si necesitas separar por plataforma o componente:

```bash
\app-banca-movil\frontend-app\ios
\app-banca-movil\frontend-app\android
\app-banca-movil\frontend-app\web
```


---

### 4. Crear iteraciones (sprints)

1. En **Project configuration** > **Iterations**, crea un nodo general:

```bash
\Release 2025 Q1
```

2. Agrega 3 iteraciones dentro de ese nodo:

| Sprint        | Fecha de inicio | Fecha de fin  |
|---------------|------------------|----------------|
| `Sprint 1`    | 2025-01-06       | 2025-01-17     |
| `Sprint 2`    | 2025-01-20       | 2025-01-31     |
| `Sprint 3`    | 2025-02-03       | 2025-02-14     |


---

### 5. Asignar áreas e iteraciones a equipos

1. Ve a **Project Settings** > **Teams**, selecciona un equipo (ej. `frontend-app`).
2. En la pestaña **Iterations**, asigna los 3 sprints.
3. En la pestaña **Areas**, asigna solo su propia área:

```bash
\app-banca-movil\frontend-app
```

4. Repite el proceso para `backend-servicios` y `qa-automatizacion`.


---

## ✅ Resultado esperado

- Tres equipos configurados y separados por función.
- Áreas definidas para agrupar work items según módulo funcional.
- Iteraciones creadas para el ciclo de trabajo `Q1 2025`.
- Cada equipo tiene su propio backlog y puede trabajar de forma paralela y organizada.

---

## 📚 Recursos adicionales

- [Configurar equipos en Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/organizations/settings/manage-teams)
- [Configurar áreas e iteraciones](https://learn.microsoft.com/en-us/azure/devops/organizations/settings/manage-areas)
- [Planificación de sprints con Azure Boards](https://learn.microsoft.com/en-us/azure/devops/boards/sprints/sprint-planning-tools)
