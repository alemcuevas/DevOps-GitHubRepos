# 🧪 Lab 6.3: Gestión de accesos y uso de Service Connections

En este laboratorio aprenderás a controlar quién puede realizar acciones en tu proyecto DevOps y cómo configurar una **Service Connection** segura para conectar Azure Pipelines con recursos de Azure como App Services, Key Vault, Storage, entre otros.

---

## 🎯 Objetivo

- Configurar permisos de acceso a repositorios y pipelines  
- Crear una Service Connection con alcance controlado  
- Usar la conexión en un pipeline para automatizar acciones  

---

## 👥 Parte 1: Configuración de acceso por rol

1. Ve a `Project Settings > Permissions`  
2. Revisa los siguientes grupos y asigna roles adecuados:

| Grupo                 | Permiso mínimo recomendado         |
|-----------------------|------------------------------------|
| Project Administrators | Full access                        |
| Contributors           | Contribute, no delete              |
| Readers                | Read-only                          |
| Service Accounts       | Contribute en pipelines o repos    |

3. Para cada grupo, revisa permisos específicos en:

- `Repos > Security`  
- `Pipelines > Security`  
- `Environments > Security`  

> Evita asignar permisos directos a usuarios individuales.

---

## 🔐 Parte 2: Crear una Service Connection

1. Ve a `Project Settings > Service connections`  
2. Haz clic en **New service connection**  
3. Elige `Azure Resource Manager`  
4. Selecciona el método de autenticación:

- **Service principal (automatic)**: más sencillo  
- **Service principal (manual)**: más controlado  
- **Managed Identity**: si estás usando agentes hospedados en Azure

5. Asigna un nombre claro como:  
   `SC-Azure-Dev` o `SC-Prod-Deploy`

6. Elige el scope de acceso:  
   - Subscription completa  
   - Resource group específico (recomendado)

---

## ⚙️ Parte 3: Usar la Service Connection en el pipeline

1. En tu archivo `azure-pipelines.yml`, en la etapa de despliegue, usa:

azureSubscription: 'SC-Azure-Dev'

2. Prueba el despliegue y verifica en Azure DevOps que la conexión se utilice correctamente

---

## ✅ Buenas prácticas

- Usa nombres claros para las conexiones según el entorno  
- Asigna permisos de uso solo al grupo de Pipelines que la necesita  
- No compartas credenciales asociadas al SPN  
- Revisa y renueva el secreto del Service Principal periódicamente  
- Usa `Managed Identity` si trabajas con Azure agentes hospedados  
- Documenta en qué pipelines se utiliza cada conexión

---

## 📚 Recursos adicionales

- Crear una Service Connection: https://learn.microsoft.com/en-us/azure/devops/pipelines/library/service-endpoints  
- Asignar permisos a conexiones: https://learn.microsoft.com/en-us/azure/devops/pipelines/library/service-endpoints#security  
- Azure CLI con Service Connections: https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/deploy/azure-cli

