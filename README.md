# 📘 Documentación del Proyecto Final - Tech Mahindra Code Challenge

## 📑 Índice

1. [Aplicación de Metodología y Gestión de Proyectos (M1)](#1-aplicación-de-metodología-y-gestión-de-proyectos-m1)
2. [Diseño - Diagrama de Arquitectura (M2)](#2-diseño---diagrama-de-arquitectura-m2)
3. [Desarrollo (M3, M4 y Reto)](#3-desarrollo-m3-m4-y-reto)
4. [Calidad (M5)](#4-calidad-m5)
5. [Deployment (M3 y Reto)](#5-deployment-m3-y-reto)
6. [CI/CD con GitHub Actions](#6-cicd-con-github-actions)
7. [ReadMe Actualizado](#7-readme-actualizado)
8. [Seguimiento del Reto](#8-seguimiento-del-reto)

---

## 1. Aplicación de Metodología y Gestión de Proyectos (M1)

- **Cierres de Sprints:** Se realizaron entregas iterativas cada semana con objetivos claros.
- **Seguimiento de Historias de Usuario:** Seguimiento continuo en herramientas como Trello / GitHub Projects.
- **Cumplimiento de Requisitos:** Cada historia de usuario fue validada con criterios de aceptación.
- **Adherencia al manifiesto ágil:** Priorizamos individuos, software funcionando, colaboración con cliente y respuesta ante el cambio.
- **Satisfacción del Cliente:** Feedback continuo, adaptaciones rápidas.
- **Lecciones Aprendidas:** 
  - Mayor sincronía con el equipo.
  - Reuniones Daily ayudan a detectar bloqueos tempranos.
  - Importancia de escribir código limpio desde el inicio.

---

## 2. Diseño - Diagrama de Arquitectura (M2)

- **Componentes Internos**
  - UI: Frontend (React + Tailwind)
  - Integración: API Gateway en Go
  - Almacenamiento: PostgreSQL, Redis
- **Componentes Externos**
  - Clerk (Auth)
  - SonarQube (Calidad)
  - Judge0 (Ejecución de código)
  - GitHub, Docker Hub

📌 **Diagrama de arquitectura:**
![Diagrama](./docs/diagrama-arquitectura.png)  
🔗 [Ver Diagrama en tamaño completo](https://github.com/tuusuario/tu-repo/blob/main/docs/diagrama-arquitectura.png)

📌 **Tecnologías por componente:** Ver tabla en sección de desarrollo.

---

## 3. Desarrollo (M3, M4 y Reto)

- ✅ **Prettier + ESLint + Husky:** Configuración para asegurar estilo y calidad en commits.
- ✅ **Buenas Prácticas:** Código limpio, reutilizable, sin repeticiones.
- ✅ **Estructura del Proyecto:**
  - `/pages`: Vistas principales
  - `/components`: Componentes UI
  - `/hooks`, `/utils`: Funcionalidades reutilizables
- ✅ **Uso correcto de features:**
  - Props bien tipadas, composición de componentes, separación lógica.
- ✅ **ORM y BD:**
  - Uso de Prisma/SQL para conexión entre frontend y base de datos en Go API.

📁 Ver estructura del proyecto en `docs/estructura-proyecto.png`

---

## 4. Calidad (M5)

- ✅ **Casos de prueba documentados:**
  - 1 caso de prueba por cada historia de usuario.
- ✅ **Pruebas automatizadas:**
  - Cada integrante contribuyó con 10 pruebas usando:
    - `Vitest` para componentes
    - `Cypress` para integración
    - `Jest` para funciones puras
- ✅ **End-to-End (Cypress):**
  - Login y envío de código correctamente validados.
- ✅ **Evidencia de ejecución:**
  - `TestRun #1` - Manuales (cobertura 30%)
  - `TestRun #2` - Automatizadas

📁 Ver carpeta `/evidencias/` con capturas de ejecución.

---

## 5. Deployment (M3 y Reto)

- ✅ Aplicación desplegada en servidor con Docker Compose.
- Frontend en http://142.93.10.227:5173/
- Backend accesible mediante contenedor con API.
- Configuraciones para entorno `.env` y producción.

---

## 6. CI/CD con GitHub Actions

- ✅ Linting automático con cada PR.
- ✅ Tests automáticos con Jest/Vitest.
- ✅ Docker build & deploy:
  - Revisión y pruebas antes de producción.

---

## 7. ReadMe Actualizado

- Índice funcional
- Diagrama embebido
- Evidencia clara y documentada
- Seguimiento de desarrollo y calidad

---

## 8. Seguimiento del Reto

📹 **Video funcionalidad de la aplicación:**  
[🔗 Ver video en Drive](https://drive.google.com/your-link)

📊 **Presentación final:**  
[🔗 Ver presentación](https://docs.google.com/presentation/your-link)

---

