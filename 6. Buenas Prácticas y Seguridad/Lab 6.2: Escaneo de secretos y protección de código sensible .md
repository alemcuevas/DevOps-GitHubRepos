# 🧪 Lab 6.2: Escaneo de secretos y protección de código sensible

En este laboratorio habilitarás mecanismos para escanear tu código y detectar posibles filtraciones de secretos como claves API, tokens de acceso, contraseñas o certificados. Esto te ayudará a prevenir riesgos de seguridad derivados de errores comunes durante el desarrollo.

---

## 🎯 Objetivo

- Detectar secretos accidentalmente expuestos en el repositorio  
- Configurar herramientas automáticas de escaneo  
- Integrar validaciones al pipeline de CI  

---

## 🧠 Parte 1: ¿Qué se considera un secreto?

- Claves de API (ej. `AIzaSy...`)  
- Tokens personales (PATs, JWTs, OAuth)  
- Contraseñas incrustadas en variables o archivos  
- Certificados o claves privadas  
- Strings que coinciden con patrones de servicios como Azure, AWS, Google Cloud

---

## 🔐 Parte 2: Activar protección en GitHub (si aplica)

Si tu repositorio está en GitHub:

1. Ve a `Settings > Code security and analysis`  
2. Activa **Secret scanning** y **Push protection**  
3. GitHub escaneará automáticamente cada commit y Pull Request

---

## ✅ Buenas prácticas

- Nunca almacenar secretos en archivos de código o YAML  
- Usar Azure Key Vault o variables protegidas en pipelines  
- Rastrear exposiciones históricas y rotar secretos si se detectan  
- Automatizar los escaneos en cada ejecución del pipeline  
- Notificar al equipo cuando se bloquee un push o se detecte un secreto

---

## 📚 Recursos adicionales

- Gitleaks: https://github.com/gitleaks/gitleaks  
- Azure Key Vault en pipelines: https://learn.microsoft.com/en-us/azure/devops/pipelines/library/variable-groups#link-secrets-from-an-azure-key-vault  
- GitHub secret scanning: https://docs.github.com/en/code-security/secret-scanning/about-secret-scanning  
- Microsoft Security DevOps (alternativa integrada): https://learn.microsoft.com/en-us/security/devops/overview

