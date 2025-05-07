### 1. Crea el repositorio en GitHub

1. Abre tu navegador y accede a: [https://github.com/new](https://github.com/new)
2. Completa los siguientes campos:

   - **Repository name**: `app-banca-movil`
   - **Description**: `Proyecto web para laboratorio de Azure DevOps - Banca Móvil`
   - **Visibility**: `Public`
   - ❌ **No marques** la casilla "Initialize this repository with a README"

3. Haz clic en **"Create repository"**

![image](https://github.com/user-attachments/assets/9fb58357-c06a-4435-8542-f2fe9621e0e1)

![image](https://github.com/user-attachments/assets/dd841cc9-8692-4e9a-81b4-35fceaa41fae)

![image](https://github.com/user-attachments/assets/d5923487-f5f0-4cd8-a8a1-8b59e2db4167)

![image](https://github.com/user-attachments/assets/a3ae1b03-bfac-4f93-99b8-d0146a8970cf)

---

### 2. Conecta tu proyecto local al repositorio remoto

1. Abre una terminal en la raíz del proyecto `app-banca-movil`

2. Ejecuta los siguientes comandos:

```bash
git init
git add .
git commit -m "Primer commit"
git branch -M main
git remote add origin https://github.com/tu-usuario/app-banca-movil.git
git push -u origin main
```

<img width="625" alt="image" src="https://github.com/user-attachments/assets/27dc43ce-e5cf-4e1f-a7f7-313845fe23a1" />
