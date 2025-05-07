# 🧪 Lab 2.3: Conectar tu repositorio GitHub a Azure DevOps

En este laboratorio conectarás tu repositorio `app-banca-movil` en GitHub a tu proyecto `app-banca-movil` dentro de la organización `core-banca-ti` en Azure DevOps. Esta integración permitirá rastrear commits, pull requests y ejecutar pipelines CI/CD.

---

## 🛠️ Parte 1: Conectar GitHub mediante Service Connection

### 1. Accede a Azure DevOps

- Ve a [https://dev.azure.com](https://dev.azure.com)
- Abre la organización: `core-banca-ti`
- Selecciona el proyecto: `app-banca-movil`

---

### 2. Crear una conexión de servicio con GitHub

<img width="511" alt="image" src="https://github.com/user-attachments/assets/5184e2ec-eff0-41ed-b377-1e9e2ef66152" />

1. Ve a **Project Settings** > **Boards** > **GitHub Connections**
2. Haz clic en **Connect your GitHub Account**
5. Aparecerán dos opciones adicionales:
   - **OAuth** (recomendado si estás autenticado en VS Code/GitHub)
   - **Personal Access Token** (si necesitas tokens manuales)
  
<img width="308" alt="image" src="https://github.com/user-attachments/assets/46b5f06b-fa3b-412e-9a7a-0921a1135176" />

<img width="599" alt="image" src="https://github.com/user-attachments/assets/5815e4fe-0693-4505-9d6f-6063a246e220" />

---

![image](https://github.com/user-attachments/assets/bc1ed900-3b23-49ce-bdd2-6da90b70bd17)
## ⚙️ Secciones de configuración de un repositorio en Azure DevOps

En Azure DevOps, cada repositorio tiene varias secciones de configuración disponibles en **Repos > Settings**, que permiten controlar cómo se gestiona el código, quién puede acceder a él, y bajo qué reglas debe operar.

A continuación se detallan las principales secciones:

---

### 🛠️ Settings

Esta sección permite definir la configuración general del repositorio.

- **Default branch**: Establece la rama principal (`main`, `develop`, etc.).
- **Clean up policies**: Opcional para eliminar ramas automáticamente tras merges.
- **Git LFS**: Habilita soporte para archivos grandes.
- **Commit sign-off**: Obliga a los usuarios a firmar sus commits.
- **Contributors can push to default branch**: Puede restringirse según política.

> ✅ Recomendación: Establecer `main` como rama por defecto y deshabilitar push directo a ramas protegidas.

---

### 🔒 Security

Controla **quién puede acceder** al repositorio y **qué acciones puede realizar**.

- **Read**: Ver el contenido del repositorio.
- **Contribute**: Realizar push/pull y crear ramas.
- **Branch permissions**: Permisos específicos por rama (ej. `main` solo lectura).
- **Manage permissions**: Permite cambiar estos niveles a otros usuarios o grupos.

> ✅ Recomendación: Asignar permisos por grupo (Dev, QA, PM), no por usuario individual.

---

### 📏 Policies

Define las **reglas que deben cumplirse** antes de que una rama reciba cambios.

Las políticas más comunes son:

- **Require a minimum number of reviewers**: Ej. 2 revisores antes del merge.
- **Check for linked work items**: Obliga a vincular el cambio a un item de Azure Boards (AB#).
- **Check for comment resolution**: No permite merge si hay comentarios sin resolver.
- **Limit merge types**: Por ejemplo, permitir solo "Squash merge".
- **Build validation**: Ejecuta una pipeline antes de permitir el merge.
- **Status checks**: Integraciones externas pueden reportar si una condición se cumple.

> ✅ Recomendación: Activar revisores obligatorios, validación por build, y vinculación a work items para ramas protegidas.

---

### ✅ Approvals and Checks

Esta sección permite **configurar aprobaciones manuales y condiciones** antes de que se permita una operación en un repositorio o entorno (por ejemplo, un despliegue o una fusión).

- **Approvals**: Requiere que ciertas personas aprueben manualmente una operación.
- **Checks**: Validaciones automáticas (por ejemplo, que una pipeline haya pasado).
- **Protected Resources**: Controla acceso a recursos sensibles como variables de entorno o conexiones externas.

> ✅ Recomendación: Usar "Approvals and Checks" para despliegues a producción o ambientes críticos.

---

## 🧠 Consideraciones generales

| Sección             | ¿Para qué sirve?                              |
|---------------------|-----------------------------------------------|
| Settings            | Configuración técnica y de ramas              |
| Security            | Control de acceso por usuarios y grupos       |
| Policies            | Reglas que deben cumplirse antes de merges    |
| Approvals and Checks| Validaciones adicionales y aprobaciones manuales |

---

### 3. Agrega tu código a Azure Repos

1. Ve a **Repos** > **Files**

<img width="950" alt="image" src="https://github.com/user-attachments/assets/998d88bb-4671-4de5-bdb4-35895881da8c" />

2. Selecciona tu repositorio a importar:

![image](https://github.com/user-attachments/assets/6b6ad5c1-e870-4113-a6d2-11eea11a5ebf)

![image](https://github.com/user-attachments/assets/725d2820-3e17-411c-ac3f-134bd289c3f4)

![image](https://github.com/user-attachments/assets/5953f47b-ccc2-493b-b5fd-eaa91eeea299)

## 📚 Recursos adicionales

- [Branch policies](https://learn.microsoft.com/en-us/azure/devops/repos/git/branch-policies)
- [Repository settings](https://learn.microsoft.com/en-us/azure/devops/repos/git/manage-repositories)
- [Repository security and permissions](https://learn.microsoft.com/en-us/azure/devops/repos/git/permissions)
- [Approvals and checks](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/approvals)

