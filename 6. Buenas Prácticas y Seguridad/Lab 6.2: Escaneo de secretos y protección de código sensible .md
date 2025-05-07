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

## 🛠️ Parte 2: Escaneo manual con Gitleaks

1. Instala [Gitleaks](https://github.com/gitleaks/gitleaks) en tu equipo  
2. Ejecuta en tu repositorio local:

gitleaks detect --source . --report-format sarif --report-path gitleaks-report.sarif

3. Revisa si hay secretos expuestos en el historial del código

> Puedes incluir este comando en tu pipeline de CI.

---

## 🔄 Parte 3: Escaneo automático en Azure Pipelines

1. Agrega la siguiente tarea a tu pipeline de CI (`azure-pipelines.yml`):

- script: |  
    curl -sL https://github.com/gitleaks/gitleaks/releases/download/v8.18.2/gitleaks-linux-amd64 -o gitleaks  
    chmod +x gitleaks  
    ./gitleaks detect --source . --exit-code 1  
  displayName: 'Escanear secretos con Gitleaks'

2. Si Gitleaks detecta un secreto, la build fallará automáticamente

---

## 🔐 Parte 4: Activar protección en GitHub (si aplica)

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

