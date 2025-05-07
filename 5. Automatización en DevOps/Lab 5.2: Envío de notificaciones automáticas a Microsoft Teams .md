# 🧪 Lab 5.2: Envío de notificaciones automáticas a Microsoft Teams

En este laboratorio integrarás Azure DevOps con un canal de Microsoft Teams para enviar notificaciones automáticas cada vez que ocurra un evento importante, como la finalización de un pipeline o la necesidad de aprobación.

---

## 🎯 Objetivo

- Conectar Azure DevOps a Microsoft Teams  
- Enviar notificaciones automáticas de pipelines  
- Mejorar la visibilidad y colaboración del equipo

---

## 📢 Parte 1: Crear un conector en Teams

1. Abre Microsoft Teams  
2. Ve al canal donde deseas recibir notificaciones (ej. `#devops-alertas`)  
3. Haz clic en los tres puntos `...` del canal > **Conectores**  
4. Busca el conector **Azure DevOps** y haz clic en **Agregar**

5. Elige:
   - Organización: `core-banca-ti`
   - Proyecto: `app-banca-movil`
   - Tipo de eventos: builds, releases, pull requests, etc.

6. Configura las condiciones según tus necesidades (por ejemplo, solo fallos de build o aprobaciones pendientes)

---

## 🔄 Parte 2: Alternativa con Webhook personalizado

1. Si no ves el conector oficial, selecciona **Incoming Webhook** en el canal  
2. Dale un nombre (ej. `Notificaciones Azure DevOps`)  
3. Guarda la URL generada

4. En Azure DevOps:  
   - Ve a `Project Settings > Service Hooks`  
   - Crea una nueva suscripción  
   - Elige **Web Hooks** como proveedor  
   - Selecciona un evento (ej. `Build completed`)  
   - Pega la URL del webhook de Teams

---

## 🔍 Parte 3: Probar la notificación

1. Ejecuta un pipeline de prueba  
2. Ve a tu canal de Teams  
3. Verifica que se haya recibido la notificación con estado, nombre del pipeline y duración

> Si configuraste aprobaciones en un `environment`, también puedes recibir notificaciones de espera de aprobación.

---

## ✅ Buenas prácticas

- Usa un canal dedicado como `#ci-cd` o `#despliegues`  
- No envíes notificaciones de todo; solo de eventos importantes  
- Incluye enlaces directos a builds, PRs o artefactos en el mensaje  
- Agrega etiquetas (como [DEV], [PROD]) para facilitar lectura  
- Coordina con tu equipo qué alertas deben ser silenciosas y cuáles requieren atención

---

## 📚 Recursos adicionales

- Conectar Azure DevOps a Teams: https://learn.microsoft.com/en-us/azure/devops/service-hooks/services/teams  
- Usar Incoming Webhooks: https://learn.microsoft.com/en-us/microsoftteams/platform/webhooks-and-connectors/how-to/add-incoming-webhook  
- Configurar Service Hooks en Azure DevOps: https://learn.microsoft.com/en-us/azure/devops/service-hooks/overview
