# 🧪 Laboratorio: Configuración Inicial en Azure DevOps

Este laboratorio tiene como objetivo preparar un entorno completo en Azure DevOps para la colaboración ágil, integración con GitHub y automatización de flujos de trabajo. A través de ejercicios guiados, los participantes crearán una organización, estructurarán equipos, configurarán Boards y establecerán conexiones con repositorios externos.


### 🏢 Organización

Una **organización** en Azure DevOps es una agrupación lógica que permite gestionar proyectos, usuarios, permisos y configuraciones comunes. Es el contenedor principal que agrupa todo tu trabajo.

- Tiene una URL única como: `https://dev.azure.com/<nombre-organizacion>`
- Agrupa múltiples proyectos, cada uno con su propia configuración.
- Puede estar vinculada a un Azure Active Directory (AAD).

---

### 📁 Proyecto

Un **proyecto** es una unidad de trabajo dentro de una organización. Cada proyecto puede representar una aplicación, un módulo bancario o un sistema completo (por ejemplo, banca móvil, core bancario, antifraude, etc.).

- Tiene su propio backlog, repositorio de código, pipelines y tableros.
- Soporta múltiples equipos trabajando en paralelo.

---

## ✅ Buenas prácticas de estructura

- Utiliza **nombres claros y estandarizados** para organizaciones y proyectos.
- Evita incluir nombres de ambientes (`dev`, `prod`) en el nombre del proyecto.
- Mantén un proyecto por solución o producto bancario.
- Usa descripciones precisas para facilitar el onboarding de nuevos colaboradores.
- Define una nomenclatura interna para futuros proyectos (ej. `app-<nombre>` o `mod-<nombre>`).

---

## 🔐 Consideraciones de seguridad y escalabilidad

- Usa **Azure Active Directory (AAD)** para controlar accesos por roles empresariales.
- Asigna permisos a través de **grupos de seguridad**, no a usuarios individuales.
- Mantén todos los proyectos bancarios como **privados**.
- Activa políticas de auditoría para mantener trazabilidad.
- Crea una organización diferente por unidad de negocio si hay separación legal o de seguridad.

---

## 🛠️ Pasos del laboratorio

### 1. Acceder a Azure DevOps

1. Abre el navegador y accede a: [https://dev.azure.com](https://dev.azure.com)
2. Inicia sesión con tu cuenta Microsoft.

<img width="596" alt="image" src="https://github.com/user-attachments/assets/24949277-65c2-4746-acda-2d8121ef3640" />

---

### 2. Crear una organización

1. Haz clic en el botón **"New organization"**.
2. Completa los campos con valores de ejemplo:

   - **Organization name**: `financia-banca-ti`
   - **Region**: `United States` (elige una cercana a tu operación)
   - Haz clic en **Continue**

<img width="233" alt="image" src="https://github.com/user-attachments/assets/7aae12e9-34ba-4b08-a60b-7d1be25389a2" />

---

### 3. Crear un nuevo proyecto bancario

1. Llena el formulario con los siguientes datos:

   - **Project name**: `app-banca-movil`
   - **Description**: `Aplicación móvil para clientes de Financia, con funcionalidades de consulta de saldo, movimientos y transferencias.`
   - **Visibility**: `Private`
   - **Version control**: `Git`
   - **Work item process**: `Agile`

2. Haz clic en **Create**.

<img width="563" alt="image" src="https://github.com/user-attachments/assets/f9bc7dc0-d495-41dc-8ad1-d1dc6e84f0df" />
<img width="813" alt="image" src="https://github.com/user-attachments/assets/9d6c98c0-3f1d-4cf4-9327-f96a353f464c" />

---

### 4. Explorar el nuevo proyecto

1. Accede al proyecto recién creado.
2. Familiarízate con las siguientes secciones:

   - **Boards**: para gestionar backlog y sprints.
   - **Repos**: para almacenar el código fuente.
   - **Pipelines**: para CI/CD.
   - **Test Plans**: para casos de prueba.
   - **Artifacts**: para gestión de paquetes seguros.

<img width="947" alt="image" src="https://github.com/user-attachments/assets/289f4ef3-c8a1-46b9-92f6-f12508a3f607" />

---

## ✅ Resultado esperado

Al finalizar este laboratorio, tendrás:

- Una organización creada y alineada al estándar bancario.
- Un proyecto privado inicial con un objetivo claro: una app móvil bancaria.
- Un punto de partida listo para equipos de desarrollo, QA y DevOps.

---

## 📚 Recursos adicionales

- [Crear una organización en Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/create-organization)
- [Crear y administrar proyectos](https://learn.microsoft.com/en-us/azure/devops/organizations/projects/create-project)
- [Buenas prácticas de nomenclatura en DevOps](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/naming-conventions)
