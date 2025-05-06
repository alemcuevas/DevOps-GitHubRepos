# 🧪 Lab 1: Fundamentos de GitHub y Azure DevOps

En este laboratorio aprenderás los conceptos básicos de GitHub y Azure DevOps, explorando sus interfaces, servicios principales y diferencias. Este lab es 100% exploratorio y te permitirá familiarizarte con ambas plataformas antes de integrarlas.

---

## 🎯 Objetivos

- Navegar las interfaces de GitHub y Azure DevOps
- Identificar los servicios principales de cada plataforma
- Comprender sus casos de uso individuales y combinados

---

## 🧰 Prerrequisitos

- Tener una cuenta activa en:
  - [GitHub](https://github.com/)
  - [Azure DevOps](https://dev.azure.com/) con al menos un proyecto creado
- Acceso a navegador web

---

## 🧭 Parte 1: Explorando GitHub

### 1. Inicia sesión en GitHub

- Accede a [https://github.com](https://github.com) y haz login.

![image](https://github.com/user-attachments/assets/4b74aa14-01e8-4995-bd6f-656e50121903)

---

### 2. Explora las secciones principales

- En el menú superior, identifica y da clic en:
  - **Repos**
  - **Issues**
  - **Pull requests**
  - **Actions**
  - **Projects**

<p align="center">
  <img src="https://github.com/user-attachments/assets/86d4a3e5-9471-42a1-a3f1-84cc289a7041" width="500" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/eaf43f54-b43e-4f73-a461-8cd9c2c6f55f" width="500" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/6540ad8f-4e9c-498e-a020-32111f5b3ce8" width="500" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/06938cc9-607a-4899-b94f-e27f102faf60" width="500" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/18c490e7-bf22-42a0-aa0a-5d0415419008" width="500" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/8fbd3bb9-1d92-4383-86e7-87a61db81ff3" width="500" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/615e3fe7-f630-4b58-8841-c457f6b8d095" width="600" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/f44046ed-da08-4eae-a073-1dd87946a524" width="500" />
</p>

---

### 3. Abre un repositorio

- Observa la estructura del repo: archivos, ramas, commits, README.

<p align="center">
<img width="456" alt="image" src="https://github.com/user-attachments/assets/ab55b50a-2d72-489e-a2e8-ad2442d15553" />
</p>

<p align="center">
<img width="411" alt="image" src="https://github.com/user-attachments/assets/16aa5423-7a30-4646-92fd-cbf94b77ae73" />
</p>

---

### 4. Examina GitHub Actions

- Ve a la pestaña **Actions**.

<p align="center">
<img width="827" alt="image" src="https://github.com/user-attachments/assets/3eced669-6e5f-46ed-a644-580514892686" />
</p>

<p align="center">
<img width="155" alt="image" src="https://github.com/user-attachments/assets/5019bbaa-8c56-4cc0-93d2-c516d3abe7e2" />
</p>

### ⚙️ GitHub Actions – Sección Management

El menú **Management** en GitHub Actions te permite administrar elementos avanzados relacionados con la ejecución y monitoreo de workflows. A continuación se detalla cada una de sus secciones:

---

### 🗄️ Caches

Permite ver y administrar las cachés utilizadas por los workflows.

- **¿Para qué sirve?**  
  Reutiliza artefactos como dependencias o builds previos para acelerar la ejecución de workflows (por ejemplo: `node_modules`, `pip`, `npm`, etc.).

- **Casos de uso comunes:**  
  - Proyectos con muchas dependencias.
  - Optimización de tiempo en CI.

---

### ✅ Attestations

Permite generar evidencia verificable de que un artefacto fue generado por un workflow específico.

- **¿Para qué sirve?**  
  Aporta trazabilidad y seguridad en la cadena de suministro (*supply chain security*) utilizando estándares como SLSA y herramientas como Sigstore.

- **Casos de uso comunes:**  
  - Generación de paquetes, imágenes de contenedor o binarios firmados.
  - Compliance y auditoría de builds.

---

### 🖥️ Runners

Administra los **runners autohospedados** utilizados por los workflows.

- **¿Para qué sirve?**  
  Ejecuta pipelines en infraestructura propia (servidores on-premises o máquinas en la nube), en lugar de los runners que proporciona GitHub.

- **Casos de uso comunes:**  
  - Workflows con necesidades específicas de hardware (GPU, red privada).
  - Mayor control sobre el entorno de ejecución.

---

### 📊 Usage metrics

Muestra métricas de uso general de GitHub Actions.

- **¿Para qué sirve?**  
  Permite monitorear el consumo de minutos, cantidad de ejecuciones, duración promedio, entre otros.

- **Casos de uso comunes:**  
  - Control de costos.
  - Reportes de actividad por equipo o repositorio.

---

### 🚀 Performance metrics

Muestra métricas específicas del rendimiento de los workflows.

- **¿Para qué sirve?**  
  Analiza detalles como duración por job, tiempos de espera entre pasos, eficiencia general.

- **Casos de uso comunes:**  
  - Identificar cuellos de botella.
  - Optimización de pipelines CI/CD.

---

## 🧭 Parte 2: Explorando Azure DevOps

### 1. Inicia sesión en Azure DevOps

- Accede a [https://dev.azure.com](https://dev.azure.com) y entra a tu organización.

![image](https://github.com/user-attachments/assets/dfaa7c60-17e7-49fc-9eb1-7aaf5881506a)

https://dev.azure.com/login

<img width="622" alt="image" src="https://github.com/user-attachments/assets/b3e01173-2707-4254-a888-ad697eae92f3" />


---

### 2. Abre un proyecto existente

- Dentro de un proyecto, explora:
  - **Boards**
  - **Repos**
  - **Pipelines**
  - **Test Plans**
  - **Artifacts**

<p align="center">
  <img src="https://github.com/user-attachments/assets/a20d8710-9938-42e8-8afb-c0ca758f2a85" width="130" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/256fe057-2954-4529-b8af-0697c0910f7f" width="130" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/4e82bddb-8f52-40b1-be28-5c18a4a17d35" width="130" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/9acea03d-849a-4856-86ef-f3a512097891" width="130" />
</p>

---

### 3. Examina cada sección brevemente

- **Boards:** Crea un work item de prueba.
- **Repos:** Observa los archivos.
- **Pipelines:** Observa el pipeline configurado.
- **Test Plans y Artifacts:** Explora a detalle.




---

## 📚 Recursos de apoyo

- [GitHub Docs](https://docs.github.com/)
- [Azure DevOps Docs](https://learn.microsoft.com/en-us/azure/devops/)

