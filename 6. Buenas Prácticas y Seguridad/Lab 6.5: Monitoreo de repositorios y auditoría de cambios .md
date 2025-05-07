# 🧪 Lab 6.5: Monitoreo de repositorios y auditoría de cambios

En este laboratorio configurarás capacidades de monitoreo y auditoría en Azure DevOps para registrar eventos relevantes como cambios en ramas, ajustes en pipelines, ediciones de permisos o acciones de usuarios. Esto facilita la trazabilidad y el cumplimiento en entornos regulados.

---

## 🎯 Objetivo

- Acceder al historial de auditoría de un proyecto DevOps  
- Consultar cambios en repositorios, pipelines y configuraciones  
- Activar alertas para eventos relevantes  

---

## 🔎 Parte 1: Acceder al historial de auditoría

1. Ve a [https://dev.azure.com](https://dev.azure.com)  
2. En el menú superior derecho, haz clic en el engrane > **Organization settings**  
3. En el panel lateral, haz clic en **Auditing**  
4. En el buscador, filtra eventos por:

- Fecha  
- Proyecto: `app-banca-movil`  
- Categoría: `Git`, `Pipelines`, `Security`, `Library`, etc.  
- Usuario específico

5. Verifica eventos como:

- Cambios de políticas en ramas  
- Creación o edición de pipelines  
- Cambios de permisos o roles  
- Eliminación o modificación de repositorios

> Solo usuarios con permisos de administrador de la organización pueden acceder a estos registros.

---

## ⚙️ Parte 2: Descargar registros o consultar con API

1. Dentro de la vista de auditoría, haz clic en **Export**  
2. Selecciona un rango de fechas y descarga en formato `.csv`

> Si lo necesitas, también puedes consultar los eventos usando la [Auditing REST API](https://learn.microsoft.com/en-us/rest/api/azure/devops/audit/audit-log)

---

## 📢 Parte 3: Configurar alertas por suscripción

1. Ve a `Project Settings > Notifications`  
2. Crea una nueva suscripción personalizada  
3. Filtra por evento como:  
   - `A Pull Request is updated`  
   - `A build completes`  
   - `A service connection is modified`  
4. Elige a quién notificar (correo, grupo de usuarios)

> Esto permite recibir alertas en tiempo real de cambios clave.

---

## ✅ Buenas prácticas

- Revisar logs de auditoría al menos una vez al mes  
- Activar alertas para cambios de seguridad o infraestructura  
- Exportar y conservar registros como parte de las auditorías de TI  
- Restringir el acceso a la consola de auditoría a roles operativos  
- Documentar los eventos críticos que deben ser monitoreados

---

## 📚 Recursos adicionales

- Auditoría en Azure DevOps: https://learn.microsoft.com/en-us/azure/devops/organizations/auditing  
- API de auditoría: https://learn.microsoft.com/en-us/rest/api/azure/devops/audit/audit-log  
- Configurar notificaciones: https://learn.microsoft.com/en-us/azure/devops/notifications/about-notifications

