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

<img width="464" alt="image" src="https://github.com/user-attachments/assets/5ce1b3ad-2d8a-4b4d-a3a0-d5d69cdf0b1d" />

- Para cambiar y generar templates de procesos y configurarlos:

1. Ve a la configuración de la organización:

![image](https://github.com/user-attachments/assets/10537f8d-8fb1-4c5d-bdb7-d15bef496596)

<img width="827" alt="image" src="https://github.com/user-attachments/assets/e922fb6c-8d83-4ca8-9545-2bab650c9490" />

2. Selecciona el proceso Agile:

<img width="641" alt="image" src="https://github.com/user-attachments/assets/36d2677c-ac29-4129-885b-d22dd2fcd086" />

3. Selecciona User Story:

<img width="695" alt="image" src="https://github.com/user-attachments/assets/f4b20370-6133-4d1a-bb42-1d37b75cb021" />

4. Regresa a All Processes y da click en los 3 puntos:

![image](https://github.com/user-attachments/assets/a164fbb4-bd8a-4d46-8a14-fc09046ad689)

5. Agrega un nombre al proceso como `agile-app-banca-movil`:
Description: `Agile process for our app banca movil`
<img width="259" alt="image" src="https://github.com/user-attachments/assets/a97127c2-acf2-42b0-a610-9e2ad16860c1" />
<img width="826" alt="image" src="https://github.com/user-attachments/assets/4d3bf069-2e07-45f9-afe3-2515c2aa28f5" />

6. Entra al nuevo proceso que creaste:
<img width="826" alt="image" src="https://github.com/user-attachments/assets/cfb6f559-c18c-40b0-9211-98914e738856" />

7. Da click en `+ New work item type`

8. Da click en `User Story`

<img width="686" alt="image" src="https://github.com/user-attachments/assets/7b7f2106-4c1d-41a2-ac61-19c2923efaf0" />

9. Ve a All processes, Agile y da click en los tres puntos:
    
<img width="578" alt="image" src="https://github.com/user-attachments/assets/0438ab3f-615d-4935-a88e-d01b18939858" />

10. Selecciona nuestro nuevo proceso.
<img width="228" alt="image" src="https://github.com/user-attachments/assets/3ce91272-1f3b-493e-9536-c5c899b859e4" />


---

## 👥 Parte 2: Configurar el equipo y áreas

1. Ve a `Project Settings` > `Teams`
   
![image](https://github.com/user-attachments/assets/fa4191da-4f6b-4166-bf32-abb38f19d410)

2. Si no existe, crea un equipo llamado `Desarrollo App Banca`
   
<img width="230" alt="image" src="https://github.com/user-attachments/assets/bb975e8c-f515-48cc-8f26-0554725f2e68" />

3. Asigna miembros al equipo (puedes usar tu cuenta y otras de prueba)

4. Ve a `Project Settings` > `Project Configuration`
5. Define un **área** específica para el equipo:
   - `app-banca-movil\Desarrollo`
  
![image](https://github.com/user-attachments/assets/7b9535db-1042-4324-bcd6-521a8093d774)

6. Asocia el área al equipo desde su configuración (`Boards > Team Configuration`)

<img width="680" alt="image" src="https://github.com/user-attachments/assets/f5cb6f23-7dd4-4023-bd20-d6ff94185cfb" />

> ✅ Consejo: Usa áreas para dividir el trabajo por producto, módulo o responsabilidad del equipo.

---

## 📅 Parte 3: Configurar sprints y calendario

1. Ve a `Project Settings` > `Boards` > `Project configuration`
2. Define la estructura de iteraciones (sprints):

   - `Sprint 1` – Fecha inicio: hoy | Fecha fin: +2 semanas
   - `Sprint 2` – Fecha inicio: +2 semanas | Fecha fin: +4 semanas
   - `Sprint 3` – Fecha inicio: +4 semanas | Fecha fin: +6 semanas

![image](https://github.com/user-attachments/assets/c50c5cf6-901f-4255-9617-5f4a90f4c992)

3. Regresa a `Boards > Sprints` y confirma que las iteraciones aparezcan en la vista del equipo

![image](https://github.com/user-attachments/assets/e775e1e1-8725-4f09-9d24-2d9dab4d0c14)

> ✅ Recomendación: Usa iteraciones regulares (quincenales o mensuales) para establecer ciclos de planificación y entrega.

---

## 📋 Parte 4: Personalizar el tablero

1. Ve a `Boards > Boards`
2. Verás el tablero Kanban del equipo con las columnas predeterminadas:

   - `New` → `Active` → `Resolved` → `Closed`

![image](https://github.com/user-attachments/assets/52f20aa1-86b9-44e5-828f-8290293e185c)

3. Haz clic en el ícono de engrane ⚙️ para personalizar columnas o estados

![image](https://github.com/user-attachments/assets/a726c43c-8c71-480d-a41e-e31e98cec405)
          
4. Puedes agregar columnas como:
   - `Ready for Dev`, `In QA`, `Ready for Release`

![image](https://github.com/user-attachments/assets/4f659a5e-ef5f-4867-8930-ec140b6a51de)

> ✅ Recomendación: Ajusta las columnas al flujo real de trabajo de tu equipo, pero no exageres en cantidad.

---

## 📚 Recursos adicionales

- [Introducción a Azure Boards](https://learn.microsoft.com/en-us/azure/devops/boards/get-started/what-is-azure-boards)
- [Configurar sprints y áreas](https://learn.microsoft.com/en-us/azure/devops/boards/sprints/set-iteration-paths)
- [Personalizar el tablero Kanban](https://learn.microsoft.com/en-us/azure/devops/boards/boards/customize-cards)

