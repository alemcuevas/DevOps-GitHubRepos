# 🧪 Lab 3.3: Configurar políticas de ramas y revisión de código

En este laboratorio configurarás políticas sobre la rama `main` del repositorio `app-banca-movil` conectado desde GitHub a tu proyecto en Azure DevOps. Estas políticas te permitirán aplicar revisiones obligatorias, validaciones automáticas y mejorar la calidad del código antes del merge.

---

## 🎯 Objetivo

- Configurar políticas de revisión y validación sobre la rama `main`
- Forzar el uso de Pull Requests
- Proteger el repositorio ante errores manuales
- Asegurar trazabilidad con Azure Boards

---

## 🛠️ Parte 1: Configurar políticas de la rama

1. Ve a [https://dev.azure.com](https://dev.azure.com)
2. Abre el proyecto: `core-banca-ti > app-banca-movil`
3. Dirígete a `Repos > Branches`
4. Busca la rama `main` y haz clic en los tres puntos `...` > **Branch policies**

![image](https://github.com/user-attachments/assets/5a2e4a89-2f8d-4455-a869-209a6955c909)

---

### Activa las siguientes políticas:

- **Require a minimum number of reviewers**
  - Valor: `2`
- **Check for linked work items**
  - Obligatorio usar `AB#<ID>` en commits o PR
- **Check for comment resolution**
  - No se permite el merge si hay comentarios sin resolver
- **Build validation** (opcional)
  - Selecciona una pipeline de CI existente (por ejemplo: `ci-app-banca`)
- **Limit merge types**
  - Habilita solo "Squash merge"
- **Automatically include code reviewers**
  - Agrega a los leads del proyecto (si están definidos)

> ✅ Recomendación: Documenta estas políticas en el README interno o en una Wiki del proyecto.

![image](https://github.com/user-attachments/assets/e827de21-3aa4-44e0-8f88-5bcc452cca31)

---

## 🔍 Parte 2: Probar las políticas

1. Crea una nueva rama `feature/test-politicas`
2. Realiza un cambio menor y súbelo a GitHub
3. Crea un Pull Request hacia `main`:
   - Asegúrate de incluir un `AB#ID`
   - Espera a que se ejecuten los pipelines y se solicite la revisión
4. Intenta hacer merge sin resolver un comentario o sin el build exitoso

> ❌ No se permitirá mientras no cumplas las condiciones.

---

## 📚 Recursos adicionales

- [Configurar políticas de rama en Azure Repos](https://learn.microsoft.com/en-us/azure/devops/repos/git/branch-policies)
- [Revisión efectiva de Pull Requests](https://learn.microsoft.com/en-us/azure/devops/repos/git/pull-request-guidance)
- [Integrar validaciones con Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/repos/github)

