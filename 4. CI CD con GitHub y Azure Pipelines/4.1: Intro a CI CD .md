## 🔄 4. CI/CD con GitHub y Azure Pipelines

La integración entre GitHub y Azure Pipelines permite implementar prácticas modernas de **CI/CD (Integración Continua y Entrega Continua)** automatizando pruebas, builds y despliegues cada vez que se actualiza el código en GitHub.

---

### 🧠 ¿Qué es CI/CD?

- **CI (Integración Continua)**: Automatiza la validación del código cada vez que se realiza un cambio, ejecutando pruebas, linters o compilación.
- **CD (Entrega Continua / Despliegue Continuo)**: Automatiza la entrega del código validado a ambientes como desarrollo, pruebas o producción.

---

### 🔗 Ventajas de GitHub + Azure Pipelines

- Utiliza GitHub como repositorio y Azure Pipelines como motor de automatización.
- Define pipelines en YAML, lo que permite control de versiones y revisiones del flujo de CI/CD.
- Compatible con múltiples lenguajes y frameworks: Node.js, .NET, Java, React, Python, etc.
- Permite la integración con Azure, Docker, Kubernetes, y servicios externos.

---

### ⚙️ Componentes de Azure Pipelines

- **Pipeline**: Secuencia de tareas para compilar, probar y desplegar.
- **Stage**: Grupo lógico de pasos (por ejemplo: build, QA, production).
- **Job**: Conjunto de tareas que corren en un agente.
- **Step o Task**: Instrucción individual (instalar, probar, copiar archivos, etc).
- **Triggers**: Eventos que activan el pipeline (push, PR, cron, manual).
- **Service Connections**: Conexiones seguras a otros sistemas (GitHub, Azure, Docker Hub, etc).

---

### 🛠️ Flujo típico de trabajo

1. Se hace un push o PR en una rama (por ejemplo, `develop`) en GitHub.  
2. Azure Pipelines detecta el evento y activa el pipeline.  
3. Se ejecutan tareas como instalación de dependencias, pruebas, linting y compilación.  
4. Si es `main` o `release`, se ejecuta el despliegue.  
5. Se notifican resultados o se vinculan al board correspondiente.

---

### 📝 Ejemplo de YAML básico para un proyecto Node.js

- **trigger**:  
  - branches:  
    - include: `main`, `develop`

- **pool**:  
  - vmImage: `ubuntu-latest`

- **steps**:  
  - Task: `NodeTool`  
    - Inputs: versionSpec: `18.x`  
    - DisplayName: "Instalar Node.js"

  - Script: `npm install`  
    - DisplayName: "Instalar dependencias"

  - Script: `npm run test`  
    - DisplayName: "Ejecutar pruebas"

  - Script: `npm run build`  
    - DisplayName: "Build del proyecto"

---

### ✅ Buenas prácticas

- Define tus pipelines como archivo `azure-pipelines.yml` y colócalo en la raíz del repositorio.
- Usa ramas separadas para `develop` y `main`, y activa triggers solo para estas.
- Automatiza pruebas, validaciones de estilo y construcción del proyecto.
- Configura despliegues automáticos a ambientes de prueba, y manuales para producción.
- Usa notificaciones automáticas por correo, Teams o Slack para cada ejecución.

---

### 🔐 Seguridad y control

- Usa conexiones de servicio autenticadas con el menor scope posible.
- Activa **Approvals and Checks** antes de desplegar a ambientes sensibles.
- Asegúrate de que los pipelines no puedan ser modificados por usuarios sin permisos.

---

### 📚 Recursos adicionales

- [🔗 Configurar Azure Pipelines con GitHub](https://learn.microsoft.com/en-us/azure/devops/pipelines/repos/github)  
- [📘 Esquema YAML para Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/yaml-schema)  
- [✅ CI/CD para JavaScript](https://learn.microsoft.com/en-us/azure/devops/pipelines/ecosystems/javascript)  
- [🔒 Seguridad en pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/security/)
