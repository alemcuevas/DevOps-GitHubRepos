## 🛡️ 6.1 Buenas prácticas y seguridad en Azure DevOps

Implementar buenas prácticas de seguridad en Azure DevOps es clave para proteger el código fuente, los secretos de configuración, y evitar errores que puedan escalar hasta producción. Esta sección resume acciones concretas que mejoran la confiabilidad y el cumplimiento de tus flujos DevOps.

---

### 🔐 Seguridad en repositorios

- Usa **repositorios privados** por defecto.
- Restringe el acceso por grupo, no por usuario individual.
- Desactiva el push directo a `main` o `release`.
- Activa políticas de revisión con mínimo un revisor y build exitoso.
- Escanea los commits en busca de **secrets o credenciales** con herramientas como Microsoft Security DevOps o GitHub Advanced Security.

---

### 🔑 Gestión de secretos y tokens

- Usa **Azure Key Vault** o variables secretas protegidas en Pipelines.
- Nunca almacenes claves, tokens o contraseñas directamente en archivos YAML o en el código.
- Si usas GitHub, activa la opción para bloquear push de secretos automáticamente.
- Reemplaza secretos temporales por **Service Principals con acceso limitado**.

---

### ✅ Buenas prácticas en pipelines

- Usa **multi-stage pipelines** con separación clara entre CI y CD.
- Requiere aprobaciones manuales para ambientes críticos como producción.
- Usa plantillas y variables para centralizar configuraciones.
- Define artefactos con versionado automático para trazabilidad.
- Notifica al equipo con herramientas como Teams o Azure Boards.
- Documenta cada pipeline y sus responsables.

---

### 🔄 Control de acceso y auditoría

- Configura **grupos de seguridad** para roles como `Desarrollador`, `Líder técnico`, `Administrador`.
- Activa **auditoría de cambios** en configuración de proyectos y repos.
- Revisa periódicamente los **permisos de pipelines, conexiones de servicio y ambientes**.
- No reutilices identidades ni tokens personales.

---

### 🧠 Cultura de seguridad y colaboración

- Fomenta la revisión cruzada de Pull Requests.
- Revisa regularmente los workflows automatizados.
- Automatiza todo lo que pueda generar errores manuales.
- Asegura que el equipo conozca las políticas internas y los procedimientos de despliegue.

---

### 📚 Recursos adicionales

- [Seguridad en Azure Repos](https://learn.microsoft.com/en-us/azure/devops/repos/git/security)
- [Buenas prácticas para pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/best-practices)
- [Key Vault en Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/library/variable-groups?view=azure-devops&tabs=designer#link-secrets-from-an-azure-key-vault)

