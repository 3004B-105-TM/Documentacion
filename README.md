# 📘 Documentación del Proyecto Final - Tech Mahindra Code Challenge

📹 **Video funcionalidad de la aplicación:**  
[![Ver Video](https://img.youtube.com/vi/v5wk9jZ-Slo/0.jpg)](https://www.youtube.com/watch?v=v5wk9jZ-Slo)

** Link de la página:**  http://142.93.10.227:5173/

## 📑 Índice

1. [Aplicación de Metodología y Gestión de Proyectos (M1)](#1-aplicación-de-metodología-y-gestión-de-proyectos-m1)
2. [Diseño - Diagrama de Arquitectura (M2)](#2-diseño---diagrama-de-arquitectura-m2)
3. [Desarrollo (M3, M4 y Reto)](#3-desarrollo-m3-m4-y-reto)
4. [Calidad (M5)](#4-calidad-m5)
5. [Deployment (M3 y Reto)](#5-deployment-m3-y-reto)
6. [CI/CD con GitHub Actions](#6-cicd-con-github-actions)
7. [Seguimiento del Reto](#7-seguimiento-del-reto)

---

## 1. Aplicación de Metodología y Gestión de Proyectos (M1)

- **Cierres de Sprints:** Se realizaron entregas iterativas cada 5 semanas con objetivos claros.
- **Seguimiento de Historias de Usuario:** Seguimos y terminamos features, supervisando via GitHub Projects.
- **Cumplimiento de Requisitos:** Cada historia de usuario fue validada con criterios de aceptación. Una fue quitada, tras una sesión con socio (implementar SonarQube en repositorio).
- **Adherencia al manifiesto ágil:** Priorizamos individuos, software funcionando, colaboración con cliente y respuesta ante el cambio.
- **Satisfacción del Cliente:** Feedback continuo, adaptaciones rápidas. Les agrado nuestra solución, y en la presentación no recibimos comentarios negativos.
- **Lecciones Aprendidas:** 
  - Reuniones Daily ayudan a detectar bloqueos tempranos, resolver dudas.
  - Importancia de escribir código limpio desde el inicio.
  - Mantener estructura estable en repositorio para tener mejor comprensión en equipo.
---

## 2. Diseño - Diagrama de Arquitectura (M2)

Esta sección describe la arquitectura de alto nivel de la solución, incluyendo los componentes internos y externos utilizados. También se presenta un desglose tecnológico por componente al final de esta sección.

###  Componentes Internos (Clasificados por Capa)

#### 1. UI (Interfaz de Usuario)

* `Frontend Web (React + Tailwind)`
  Aplicación web que permite a los usuarios interactuar con el sistema.

#### 2. Capa de Integración / Servicios
* `API Backend (Go)`
  Maneja el enrutamiento de solicitudes entre el frontend, la base de datos, y el worker de ejecución de código.
* `Servicio de ejecución de código (Go + Docker)`
  Ejecuta código en contenedores seguros por lenguaje.
* `Servicio de autenticación centralizado (Clerk)`
  Maneja autenticación y autorización en todos los módulos.

#### 3. Almacenamiento / Persistencia

*  `Base de datos (PostgreSQL)`
  Guarda datos de usuario, tienda, resultados de las ejecuciones y datos de los desafíos.
*  `Redis`
  Utilizado para colas de ejecución y almacenamiento temporal de trabajos.

---

###  Componentes Externos


* `SonarQube`
  Analiza la calidad del código fuente del frontend y backend.
* `Clerk`
  Se encarga de autenticación de usuarios.
* `Github`
  Se encarga de manejo de versiones de código, hostear repositorio.
* `Aiven`
  Se encarga de hostear nuestra base de datos.
* `Digital Ocean`
  Proovedor de nuestra Maquina Virtual, donde hosteamos nuestro proyecto.
  
---

## Diagrama de arquitectura

![Captura de pantalla 2025-06-11 124142](https://github.com/user-attachments/assets/96980e10-7ecb-4683-a019-67c9c034dc5d)

---

###  Tecnologías por Componente (Detalle)

| Componente                    | Tecnología / Lenguaje    |
| ----------------------------- | ------------------------ |
| Frontend Web                  | React, TailwindCSS       |
| API Backend                   | Go                       |
| Servicio de ejecución         | Go, Docker               |
| Contenedores de ejecución     | Python, Node.js, C++, C# |
| Base de datos                 | PostgreSQL               |
| Cola de trabajos              | Redis                    |
| Calidad de código             | SonarQube                |
| Autenticación                 | Clerk                    |
| Hostear DB                    | Aiven Console            |
| Maquina Virtual               | Digital Ocean            |
---

## 3. Desarrollo (M3, M4 y Reto)

Durante el desarrollo del proyecto se implementaron diversas herramientas, convenciones y estructuras para asegurar calidad en el código, coherencia entre componentes y facilidad de mantenimiento.

### ✅ Herramientas de Calidad

#### 🧼 Prettier
- Se utilizó la extensión de **Prettier** en todos los entornos locales de desarrollo.
- Se encargó del **formateo automático del código** siguiendo convenciones consistentes: indentación, uso de comillas, punto y coma, y orden en las propiedades de los objetos.

#### 🔎 SonarQube
- Integrado como herramienta de análisis estático de código.
- Se ejecutaron escaneos para:
  - Detectar código duplicado.
  - Promover el uso de buenas prácticas.
  - Identificar posibles vulnerabilidades o malas implementaciones.
- Se resolvieron advertencias relacionadas con la legibilidad, estructura y calidad general del código.

### 🧱 Estructura del Proyecto

Aunque no se utilizó **Next.js**, se siguieron convenciones inspiradas en sus buenas prácticas:

/src
/pages             → Vistas principales del sistema
      /components  → Componentes específicos de página si llegaba a código muy largo / saturado para mejorar lectura
/components        → Componentes reutilizables
/hooks             → Lógica de React personalizada
/utils             → Funciones auxiliares y helpers
/services          → Funciones de conexión con la API
/styles            → Archivos de estilos globales o específicos


- **Componentes puros y desacoplados**
- Separación de lógica visual, lógica de estado y lógica de conexión

---

## 4. Calidad (M5)
### Historias de Usuario: 
Se puede ver funcionales en video demo.
#### HU-001 - Login de Usuario
**Descripción:** Como usuario y trabajador de la empresa, quiero poder ingresar a la plataforma.  
**Criterios de Aceptación:**
- Ingreso con correo y contraseña.
- Permitir uso de cuenta Google para mayor velocidad.
- Mensaje de error si son incorrectos o inválidos.
  
**Caso de uso**

  ![image](https://github.com/user-attachments/assets/f4a9411d-d099-47b1-ad77-9a9666beb910)
---

#### HU-002 - Resolver Problemas de Programación
**Descripción:** Como usuario, quiero poder acceder a los problemas de programación para resolverlos.  
**Criterios de Aceptación:**
- Ingresar correctamente.
- Acceder a sección “Problemas de programación”.
- Seleccionar problema a resolver.
- Obtener XP y puntos en caso de responder correctamente.

**Caso de uso**

  ![Captura de pantalla 2025-03-09 173425](https://github.com/user-attachments/assets/da73723c-a7cc-4c73-bedb-00d23e5a4d3a)

---

#### HU-003 - Filtrar Problemas
**Descripción:** Como usuario, quiero filtrar problemas por dificultad y etiquetas.  
**Criterios de Aceptación:**
- Opciones de filtro visibles.
- Lista actualizada automáticamente.
- Posibilidad de quitar filtros.

**Caso de uso**
  
  ![Captura de pantalla 2025-06-11 205221](https://github.com/user-attachments/assets/20b44053-3ece-4ca5-b924-320a2e6e797a)

---

#### HU-004 - Ver Detalles del Problema
**Descripción:** Como usuario, quiero ver la descripción completa del problema.  
**Criterios de Aceptación:**
- Página con descripción al hacer clic.
- Mostrar dificultad, etiquetas y link original.
- Botón para regresar.

**Caso de uso**

 ![Captura de pantalla 2025-06-11 205221](https://github.com/user-attachments/assets/c8f5c5e1-9017-4677-8862-ef9dd28eddcd)

---

#### HU-005 - Escribir y Ejecutar Código
**Descripción:** Como usuario, quiero escribir y ejecutar mi código para comprobar si funciona.  
**Criterios de Aceptación:**
- Editor integrado.
- Botón “Ejecutar” que envía a VM don de se crea contenedor en lenguaje.
- Resultados mostrados en la interfaz.

**Caso de uso**

![Captura de pantalla 2025-06-11 205822](https://github.com/user-attachments/assets/0c199293-7c66-42f5-ab26-2bb54eaf9f54)

---

#### HU-006 - Sistema de Recompensas
**Descripción:** Como usuario, quiero recibir XP y puntos  al resolver problemas.  
**Criterios de Aceptación:**
- Código válido actualiza puntos para tienda.
- Notificación de éxito.
- Actualización en perfil.
- Solo puede comprar usuario si alcanza por puntos y quedan productos disponibles.

**Caso de uso**

  ![Captura de pantalla 2025-06-11 205101](https://github.com/user-attachments/assets/95ae88f8-8a4d-4436-aa45-ac6be848ebe0)

---

#### HU-007 - Dashboard de Avances
**Descripción:** Como usuario, quiero ver mi avance y el de mis compañeros.  
**Criterios de Aceptación:**
- Acceder a información de otros usuarios.

**Caso de uso**

 ![Captura de pantalla 2025-06-11 204641](https://github.com/user-attachments/assets/2e38d060-f3b7-49a6-9cb5-3a7aff7059c8)

---

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

- Frontend en http://142.93.10.227:5173/
---

## 6. CI/CD con GitHub Actions

- ✅ Linting automático con cada PR.
- ✅ Tests automáticos con Jest/Vitest.
- ✅ Docker build & deploy:
  - Revisión y pruebas antes de producción.



## 8. Seguimiento del Reto


📊 **Presentación final:**  
[tm_final.pdf](https://github.com/user-attachments/files/20701967/tm_final.pdf)

---

