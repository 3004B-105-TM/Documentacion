# 📘 Documentación del Proyecto Final - Tech Mahindra Code Challenge

📹 **Video funcionalidad de la aplicación:**  
[![Ver Video](https://img.youtube.com/vi/v5wk9jZ-Slo/0.jpg)](https://www.youtube.com/watch?v=v5wk9jZ-Slo)

**Link de la página:**  http://142.93.10.227:5173/

**Cuenta normal:**   Pueden crear una, solo den sign in con Google.


**Cuenta admin:**  

**email:** a01284623@tec.mx         **password:** admin_cc10!

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



[Link Documentación completa: Carpeta Calidad](https://github.com/3004B-105-TM/Documentacion/blob/main/Calidad/README.md)

 
- ### **Pruebas automatizadas :**


  - Cada integrante contribuyó con 10 pruebas usando:
    - `Vitest` para componentes
    - `Cypress` para integración
    - `Jest` para funciones puras
- ✅ **End-to-End (Cypress):**
  - Login y envío de código correctamente validados.
- ✅ **Evidencia de ejecución:**

Ver carpeta `/tests/` con capturas de ejecución, carpeta en front (tests- persona) tiene sus archivos-

correr npx vitest en tm-front

---

## 5. Deployment (M3 y Reto)

- Frontend en http://142.93.10.227:5173/
---

Corrimos todo con el siguiente archivo bash:
```bash
#!/bin/bash

# Function to print section headers
print_header() {
    echo "==========================================="
    echo "$1"
    echo "==========================================="
}

# Function to check and kill process using a port
kill_port() {
    local port=$1
    local pid=$(lsof -t -i:$port)
    if [ ! -z "$pid" ]; then
        echo "Killing process $pid using port $port"
        kill $pid
        sleep 2
    fi
}

# Update backend
print_header "Updating Backend Service"
cd code-execution-service

# Kill any processes using the required ports
kill_port 8080  # API port
kill_port 8081  # Worker port
kill_port 6380  # Redis port

# Clean up and restart
docker-compose down
docker-compose up -d --build
echo "Backend service updated and restarted"

# Update frontend
print_header "Updating Frontend Service"
cd ../tm-front
npm install
npm run build
systemctl restart tm-front.service
echo "Frontend service updated and restarted"

print_header "All services have been updated!"
echo "Backend API: http://localhost:8080"
echo "Frontend: http://localhost:5173"

# Verify services are running
print_header "Verifying Services"
echo "Checking backend containers..."
docker ps | grep code-execution-service
echo "Checking frontend service..."
systemctl status tm-front.service | grep "Active:"
```

Gracias a este ejecutable, pudimos facilmente verificar pruebas de ejecutadores en cada lenguaje, verificar que tanto front end y backend esten activos, y actualizar (despues de hacer git pull en cada repositorio).


## 6. CI/CD con GitHub Actions

- ✅ Linting automático con cada PR.
- ✅ Tests automáticos con Jest/Vitest. (ver documentación Tests y Calidad)
- ✅ Docker build & deploy:
  - Revisión y pruebas antes de producción.



## 8. Seguimiento del Reto


📊 **Presentación final:**  
[tm_final.pdf](https://github.com/user-attachments/files/20701967/tm_final.pdf)

---

