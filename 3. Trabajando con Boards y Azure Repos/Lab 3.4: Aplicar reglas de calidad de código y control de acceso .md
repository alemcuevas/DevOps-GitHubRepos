# 🧪 Lab 3.4: Aplicar reglas de calidad de código y control de acceso

En este laboratorio configurarás controles en el repositorio `app-banca-movil` para asegurar la calidad del código fuente y limitar el acceso de los usuarios según su rol. También aplicarás integraciones con herramientas que permitan validar automáticamente el estado del código.

---

## 🎯 Objetivo

- Configurar reglas de acceso en el repositorio
- Activar herramientas de análisis de calidad de código
- Reforzar seguridad mediante permisos granulares y revisión de cambios

---

## 🛠️ Parte 1: Control de acceso al repositorio

1. Accede a [https://dev.azure.com](https://dev.azure.com)
2. Abre el proyecto: `core-banca-ti > app-banca-movil`
3. Ve a `Repos > Repositories` y luego haz clic en `Repository Settings`

4. En la sección **Security**

5. Revisa los permisos para cada grupo:

| Grupo                 | Permisos recomendados       |
|-----------------------|-----------------------------|
| `Project Administrators` | Full access                |
| `Developers`             | Contribute (sin delete)    |
| `QA`                     | Read                       |
| `External reviewers`     | Read-only (si aplica)      |

> ✅ Recomendación: No otorgues permisos directos a usuarios individuales. Usa grupos y roles definidos.

![image](https://github.com/user-attachments/assets/85ae4105-5fd2-4d8d-b344-1ff2a61e416e)

---

## 🔐 Parte 3: Activar protección contra errores

1. Ve a `Repos > Branches` y abre las políticas de la rama `main`
2. Asegúrate de que la política **Build validation** esté activada y vinculada al pipeline que contiene las validaciones
3. Opcional: Agrega validación de comentarios resueltos y status checks externos

---

## ✅ Buenas prácticas

- Agrega linters y pruebas de calidad al pipeline, no como paso manual
- Usa `tags` o convenciones para distinguir versiones validadas
- Requiere aprobación antes de fusionar código con errores de estilo o advertencias críticas
- Documenta las reglas de estilo y convenciones del repositorio en un archivo `CONTRIBUTING.md`

---

## 📚 Recursos adicionales

- [Control de acceso en repositorios Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/repos/git/security)
- [Integrar SonarCloud en Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/test/sonarqube)
- [Microsoft Security DevOps](https://learn.microsoft.com/en-us/security/devops/overview)
