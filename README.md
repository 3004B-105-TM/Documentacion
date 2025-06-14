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

- ✅ **Pruebas automatizadas :**
  - SonarQube:
  - ![Captura de pantalla 2025-06-10 084001](https://github.com/user-attachments/assets/d0bed7f6-9353-44d6-ae98-3919e46d8e7d)
 
  - ![image](https://github.com/user-attachments/assets/769e8b3d-f543-4943-9e0b-90e0f7b2c8bb)
 
  - ![image](https://github.com/user-attachments/assets/604e36ce-30a0-43b6-853e-e27df5fbb458)


  - Cada integrante contribuyó con 10 pruebas usando:
    - `Vitest` para componentes
    - `Cypress` para integración
    - `Jest` para funciones puras
- ✅ **End-to-End (Cypress):**
  - Login y envío de código correctamente validados.
- ✅ **Evidencia de ejecución:**
  - `TestRun #2` - Automatizadas

📁 Ver carpeta `/tests/` con capturas de ejecución, carpeta en front (tests- persona) tiene sus archivos-

correr npx vitest en tm-front


---
### Bitacora de pruebas

| ID de prueba | Fecha      | Probado por | Resultado esperado                                     | Resultado real                                   | Estado   | Observaciones                                              |
|--------------|------------|-------------|-------------------------------------------------------|-------------------------------------------------|----------|-----------------------------------------------------------|
| TC-001       | 01/05/2025 | Ramiro      | Usuario es redirigido al dashboard                     | Usuario fue redirigido correctamente             | Aprobada | El dashboard solo debe de ser visible si usuario ha sido autenticado |
| TC-002       | 01/05/2025 | Ramiro      | Aparece mensaje de error por credenciales inválidas   | Se mostró mensaje, pero sin estilo de alerta     | Aprobada | Hicimos validación en server y client side                |
| TC-003       | 01/05/2025 | Imanol      | Lista muestra solo problemas difíciles                 | Se filtraron correctamente                        | Aprobada | Agregar filtros por etiquetas podría ser útil             |
| TC-004       | 01/05/2025 | Imanol      | Aparecen título, descripción y ejemplos del problema  | Todo se muestra bien                              | Aprobada | Limpiar DB para solo incluir problemas válidos            |
| TC-005       | 01/05/2025 | Ramiro      | Output “Hello” se muestra en consola                    | Consola mostró “Hello”                            | Aprobada | Faltan test cases                                         |
| TC-006       | 01/05/2025 | Fer         | Se agregan puntos tras resolver problema               | Se sumaron correctamente                          | Aprobada | Se está evaluando el sistema de puntos                     |
| TC-007       | 01/05/2025 | Roger       | Dashboard muestra progreso y ranking                    | Se mostró todo correctamente                      | Aprobada | Usuario sigue hardcodeado                                  |
| TC-008       | 28/05/2025 | Fer         | El sistema funciona en diferentes lenguajes            | Ejecutó correctamente en todos los lenguajes    | Aprobada | Validado en Python, JS, C++, C#                           |
| TC-009       | 28/05/2025 | Fer         | Se confirman las compras de recompensas con lógica de negocio | Las recompensas fueron validadas correctamente | Aprobada | No permite comprar sin puntos suficientes                  |
| TC-010       | 28/05/2025 | Imanol      | Se activan badges al cumplir condiciones específicas   | Trigger activado y badge agregado correctamente  | Aprobada | Se usó trigger de nivel en PostgreSQL                      |
| TC-011       | 28/05/2025 | Roger       | Navbar nueva aparece en todas las pantallas             | Navbar visible y funcional en todas las páginas  | Aprobada | Navbar unificada implementada con nuevo diseño             |
| TC-012       | 28/05/2025 | Fer         | Los tests se ejecutan dentro del mismo contenedor Docker | Tests corrieron sin errores en entorno Dockerizado | Aprobada | Se usó un único volumen para código y pruebas              |
| TC-013       | 09/06/2025 | Fer         | El componente Leaderboard se renderiza correctamente   | Se muestra el encabezado “Rank” sin errores      | Aprobada | Verifica carga básica del componente                        |
| TC-014       | 09/06/2025 | Fer         | Se simula correctamente un usuario con useUser         | Usuario simulado como “Test User”                 | Aprobada | Uso correcto de mocking para contexto de usuario           |
| TC-015       | 09/06/2025 | Fer         | Se mockea correctamente el componente UserProfileModal | Se muestra div con texto UserProfileModal         | Aprobada | Se evita carga real del modal, prueba enfocada en Leaderboard |
| TC-016       | 09/06/2025 | Fer         | Se simula correctamente el fetch para leaderboard      | Datos mock de 4 usuarios renderizados             | Aprobada | Se devuelve respuesta simulada desde global.fetch          |
| TC-017       | 09/06/2025 | Fer         | La tabla de leaderboard se muestra correctamente        | Nombres “Alice”, “Bob”, etc. aparecen             | Aprobada | Se verifica que los datos se presentan en la tabla         |
| TC-018       | 09/06/2025 | Fer         | Se usan correctamente los temporizadores fake (vi.useFakeTimers) | Los temporizadores funcionan como esperado     | Aprobada | Útil para pruebas futuras con delays o animaciones          |
| TC-019       | 09/06/2025 | Fer         | Se limpia correctamente vi.clearAllMocks() después de cada prueba | No hay mocks persistentes entre pruebas        | Aprobada | Asegura independencia entre pruebas                         |
| TC-020       | 09/06/2025 | Fer         | Se presenta correctamente la columna de nivel (Level) en leaderboard | Nivel 100, 90, etc. aparecen junto a nombres   | Aprobada | Refleja correctamente información mockeada                  |
| TC-021       | 09/06/2025 | Fer         | El componente maneja correctamente datos sin errores en render | No hay excepciones ni advertencias al renderizar | Aprobada | Carga estable en condiciones estándar                       |
| TC-022       | 09/06/2025 | Fer         | Se verifica que todos los elementos de UI esperados estén en el DOM | Encabezados y nombres visibles con getByText y getAllBy... | Aprobada | Buena cobertura de visibilidad de contenido en el DOM     |
| TC-023       | 13/06/2025 | Imanol      | Componente Badge se renderiza correctamente con el texto esperado | Texto visible correctamente                    | Aprobada | Cubre render básico de badges con props                     |
| TC-024       | 13/06/2025 | Imanol      | El componente de ejemplo muestra su contenido de demostración | Se muestra correctamente                       | Aprobada | Puede servir como referencia para otros test                |
| TC-025       | 13/06/2025 | Imanol      | LoadingSpinner aparece durante carga                     | Se visualiza spinner                             | Aprobada | Ideal para pruebas visuales de estados de carga             |
| TC-026       | 13/06/2025 | Imanol      | Página de privacidad se muestra con contenido esperado  | Renderizó correctamente                          | Aprobada | Verificar actualización si política cambia                  |
| TC-027       | 13/06/2025 | Imanol      | Select muestra opciones y permite seleccionar una opción | Funciona como esperado                           | Aprobada | Se probaron múltiples valores                               |
| TC-028       | 13/06/2025 | Imanol      | Table muestra filas correctamente con datos mockeados   | Se muestran filas esperadas                       | Aprobada | Verificar comportamiento con filas vacías también          |
| TC-029       | 13/06/2025 | Imanol      | Página de términos se muestra correctamente con contenido legal | Todo el contenido está presente                 | Aprobada | Confirmar con equipo legal si hay cambios                   |
| TC-030       | 13/06/2025 | Imanol      | ThemeToggle cambia entre modo claro y oscuro             | Alterna correctamente el tema                     | Aprobada | Confirmar persistencia del tema entre sesiones              |
| TC-031       | 13/06/2025 | Imanol      | Componente Toaster muestra notificaciones correctamente   | Toasts visibles cuando se dispara evento          | Aprobada | Útil para pruebas de UX en notificaciones                   |
| TC-032       | 13/06/2025 | Imanol      | El sistema no lanza errores al importar y renderizar todos los componentes juntos | Todos renderizan correctamente en conjunto | Aprobada | Prueba general de compatibilidad entre componentes          |
| TC-033       | 13/06/2025 | Roger       | Visita la página de inicio correctamente                  | Página cargada con éxito                          | Aprobada | Test básico E2E que verifica carga inicial                  |
| TC-034       | 13/06/2025 | Roger       | Navegación funcional entre secciones                      | Navegación operativa (con placeholders aún)      | Aprobada | Se requiere completar pruebas de rutas específicas          |
| TC-035       | 13/06/2025 | Roger       | Componente Button renderiza y responde a eventos          | Se renderizó y respondió a clic                    | Aprobada | Cubrió comportamiento básico del botón                      |
| TC-036       | 13/06/2025 | Roger       | Card muestra correctamente el contenido hijo              | Contenido visible                                 | Aprobada | Ideal para pruebas visuales de layout                        |
| TC-037       | 13/06/2025 | Roger       | CustomButton maneja props de estilo y acción              | Se aplicaron props correctamente                  | Aprobada | Requiere pruebas con variantes                              |
| TC-038       | 13/06/2025 | Roger       | Dialog se abre/cierra y muestra contenido                  | Funcionó correctamente                            | Aprobada | Considerar prueba de accesibilidad                           |
| TC-039       | 13/06/2025 | Roger       | Input acepta texto y ejecuta eventos                        | Texto ingresado y capturado                        | Aprobada | Cubrir también validaciones en futuras pruebas              |
| TC-040       | 13/06/2025 | Roger       | Label se asocia correctamente al input                      | Asociación funcional                              | Aprobada | Verificar comportamiento en formularios complejos           |
| TC-041       | 13/06/2025 | Roger       | setup.ts ejecuta configuración previa sin errores          | Setup inicial funcionando                         | Aprobada | Necesario para otros tests, bien cubierto                    |
| TC-042       | 13/06/2025 | Roger       | ThemeProvider aplica temas correctamente en el árbol de componentes | Temas aplicados exitosamente                      | Aprobada | Confirmar persistencia y comportamiento en rutas distintas  |
| TC-043       | 13/06/2025 | Ramiro      | Component CompletedMar muestra icono correcto               | Icono y color verde renderizados correctamente    | Aprobada | Se verificó con valores true, false y null                   |
| TC-044       | 13/06/2025 | Ramiro      | ChallengeButton cambia color según estado                   | Cambió correctamente el color y bordes            | Aprobada | Test con color personalizado y estado completed false        |
| TC-045       | 13/06/2025 | Ramiro      | ChallengeButton siempre muestra ícono estrella              | Ícono estrella siempre visible                     | Aprobada | Mock de react-icons funciona correctamente                    |
| TC-046       | 13/06/2025 | Ramiro      | Mission componente muestra barra de progreso                | Barra con ancho y color correctos                  | Aprobada | Tests con y sin color personalizado                           |
| TC-047       | 13/06/2025 | Ramiro      | Mission muestra nombre y icono                               | Nombre e icono visibles                            | Aprobada | Icono de trofeo renderizado correctamente                    |
| TC-048       | 13/06/2025 | Ramiro      | Función calcula puntos correctamente                         | Puntos calculados según dificultad                | Aprobada | Validado para dificultades 1, 3 y 5                          |
| TC-049       | 13/06/2025 | Ramiro      | Manejo correcto de estados true, false, null                | Estados asignados y usados correctamente          | Aprobada | Se verifica status de problemas                              |
| TC-050       | 13/06/2025 | Ramiro      | Generación correcta de estrellas para dificultad            | Número correcto de estrellas generadas            | Aprobada | Probado para dificultad 1, 3 y 5                            |
| TC-051       | 13/06/2025 | Ramiro      | Formato correcto para puntos                                 | Puntos mostrados en formato "XX MC"                | Aprobada | Tests de formato de puntos                                  |
| TC-052       | 13/06/2025 | Ramiro      | Testeo general de componentes con mock                      | Componentes renderizados sin error                 | Aprobada | Uso de mocks para react-icons y lucide-react                |

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
- ✅ Tests automáticos con Jest/Vitest. (ver documentación Tests)
- ✅ Docker build & deploy:
  - Revisión y pruebas antes de producción.



## 8. Seguimiento del Reto


📊 **Presentación final:**  
[tm_final.pdf](https://github.com/user-attachments/files/20701967/tm_final.pdf)

---

