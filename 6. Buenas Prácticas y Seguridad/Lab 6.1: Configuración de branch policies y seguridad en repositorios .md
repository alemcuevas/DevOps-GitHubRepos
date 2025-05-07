# 🧪 Lab 6.1: Configuración de branch policies y seguridad en repositorios

En este laboratorio protegerás la rama `main` del repositorio `app-banca-movil` mediante políticas de revisión, validación y control de acceso. Aprenderás a aplicar reglas que eviten errores y aseguren trazabilidad antes del merge.

---

## 🎯 Objetivo

- Proteger la rama principal (`main`)  
- Aplicar políticas de revisión y validación  
- Configurar seguridad por roles y grupos  

---

## 🛠️ Parte 1: Acceder a la configuración de ramas

1. Ve a [https://dev.azure.com](https://dev.azure.com)  
2. Selecciona el proyecto `core-banca-ti > app-banca-movil`  
3. Navega a `Repos > Branches`  
4. Localiza la rama `main` y haz clic en los tres puntos `...`  
5. Selecciona **Branch policies**

---

## 🛡️ Parte 2: Activar políticas clave

Activa las siguientes políticas recomendadas:

- **Minimum number of reviewers**: 2  
- **Check for linked work items**: obligatorio (AB#ID)  
- **Check for comment resolution**: no permitir merge con comentarios abiertos  
- **Build validation**: seleccionar la pipeline de CI (ej. `ci-app-banca`)  
- **Limit merge types**: solo permitir squash merge  
- **Automatically include reviewers**: opcional, para equipos específicos

> Estas políticas aseguran calidad, trazabilidad y revisión colaborativa.

---

## 🔐 Parte 3: Control de acceso al repositorio

1. Ve a `Repos > Files`  
2. Haz clic en el engrane (⚙️) > **Security**

Configura permisos por grupo:

- **Project Administrators**: Full control  
- **Developers**: Contribute (sin delete)  
- **QA**: Read  
- **Stakeholders**: Read (limitado)

> No otorgues permisos individuales si no es necesario.

---

## 🔍 Parte 4: Validar con un Pull Request

1. Crea una rama `feature/prueba-policies`  
2. Realiza un cambio menor y súbelo  
3. Crea un Pull Request hacia `main`  
4. Verifica que:
   - Se requieran revisores  
   - No puedas hacer merge sin vincular un AB#ID  
   - El build de validación se ejecute  
   - Se bloquea el merge si hay comentarios abiertos

---

## ✅ Buenas prácticas

- No permitir push directo a `main`, solo vía Pull Request  
- Exigir revisiones de al menos 2 miembros del equipo  
- Rechazar PRs sin work items vinculados  
- Documentar las políticas activas en la wiki del repositorio  
- Revisar estas políticas trimestralmente

---

## 📚 Recursos adicionales

- Branch policies: https://learn.microsoft.com/en-us/azure/devops/repos/git/branch-policies  
- Seguridad en repositorios: https://learn.microsoft.com/en-us/azure/devops/repos/git/security  
- Revisión de Pull Requests: https://learn.microsoft.com/en-us/azure/devops/repos/git/pull-requests

