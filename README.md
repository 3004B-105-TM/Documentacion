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

## Plan de pruebas


### TC-001 – Login con credenciales válidas

**Historia relacionada:** HU-001 - Login de Usuario

**Objetivo:** Validar que un usuario pueda iniciar sesión correctamente.

**Datos de entrada:**
Email: [user@tech.com](mailto:user@tech.com)
Contraseña: 123456

**Pasos:**

1. Ir al formulario de login
2. Ingresar correo y contraseña válidos
3. Hacer clic en "Iniciar sesión"

**Resultado esperado:** Usuario es redirigido al dashboard.

---

### TC-002 – Login con credenciales inválidas

**Historia relacionada:** HU-001 - Login de Usuario

**Objetivo:** Mostrar mensaje de error con datos inválidos.

**Datos de entrada:**
Email: [fake@correo.com](mailto:fake@correo.com)
Contraseña: abc123

**Pasos:**

1. Ir al login
2. Ingresar correo y contraseña inválidos
3. Hacer clic en "Iniciar sesión"

**Resultado esperado:** Aparece mensaje “Credenciales incorrectas”.

---

### TC-003 – Filtro de problemas por dificultad

**Historia relacionada:** HU-003 - Filtrar Problemas

**Objetivo:** Validar filtrado por nivel de dificultad.

**Datos de entrada:** Selección: “Difícil”

**Pasos:**

1. Ir a la lista de problemas
2. Aplicar filtro por dificultad “Difícil”

**Resultado esperado:** Solo se muestran problemas con nivel difícil.

---

### TC-004 – Visualización de detalles del problema

**Historia relacionada:** HU-004 - Ver Detalles del Problema

**Objetivo:** Comprobar que se muestre descripción, entrada/salida esperada.

**Pasos:**

1. Seleccionar un problema de la lista
2. Abrir detalles del problema

**Resultado esperado:** Aparecen correctamente título, descripción, ejemplos de entrada/salida.

---

### TC-005 – Ejecutar código y mostrar resultado

**Historia relacionada:** HU-005 - Escribir y Ejecutar Código

**Objetivo:** Validar que el código se envía y devuelve el resultado esperado.

**Datos de entrada:** Código en Python (`print("Hello")`)

**Pasos:**

1. Escribir código en el editor
2. Presionar “Ejecutar”

**Resultado esperado:** Se muestra el output “Hello” en la consola.

---

### TC-006 – Recompensa al resolver problema

**Historia relacionada:** HU-006 - Sistema de Recompensas

**Objetivo:** Confirmar que se otorgan puntos al resolver correctamente un problema.

**Pasos:**

1. Resolver problema con código correcto
2. Enviar solución

**Resultado esperado:** Se muestra mensaje de éxito y se agregan puntos al usuario.

---

### TC-007 – Visualización del Dashboard

**Historia relacionada:** HU-007 - Dashboard de Avances

**Objetivo:** Validar que se muestren progreso, puntos y ranking.

**Pasos:**

1. Iniciar sesión
2. Navegar al dashboard

**Resultado esperado:** Se muestran barras de avance, medallas y datos actualizados del usuario.

---

Perfecto. A continuación te muestro los diseños de pruebas actualizados para los casos TC-001 al TC-052, utilizando únicamente las historias de usuario reales (HU-001 a HU-007). Si algún caso no tiene historia relacionada, se marca como “Sin historia de usuario relacionada”.

---

### TC-001 – Redirección tras login exitoso

**Historia relacionada:** HU-001 - Login de Usuario
**Objetivo:** Validar que el usuario autenticado sea redirigido al dashboard.
**Datos de entrada:** Email: [user@empresa.com](mailto:user@empresa.com), Contraseña: correcta123
**Pasos:**

1. Ir al formulario de login
2. Ingresar correo y contraseña válidos
3. Hacer clic en “Iniciar sesión”
   **Resultado esperado:** Usuario es redirigido al dashboard

---

### TC-002 – Login con credenciales inválidas

**Historia relacionada:** HU-001 - Login de Usuario
**Objetivo:** Validar que se muestre un mensaje de error al ingresar credenciales incorrectas.
**Datos de entrada:** Email: [falso@mail.com](mailto:falso@mail.com), Contraseña: error123
**Pasos:**

1. Ir al login
2. Ingresar datos inválidos
3. Hacer clic en “Iniciar sesión”
   **Resultado esperado:** Se muestra alerta de credenciales incorrectas

---

### TC-003 – Filtro por dificultad “Difícil”

**Historia relacionada:** HU-003 - Filtrar Problemas
**Objetivo:** Validar que solo se muestren problemas difíciles al aplicar ese filtro.
**Datos de entrada:** Dificultad: Difícil
**Pasos:**

1. Ir a sección de problemas
2. Seleccionar filtro “Difícil”
   **Resultado esperado:** Lista contiene únicamente problemas difíciles

---

### TC-004 – Ver detalles de un problema

**Historia relacionada:** HU-004 - Ver Detalles del Problema
**Objetivo:** Validar que se muestra título, descripción y ejemplos al abrir un problema
**Pasos:**

1. Ir a lista de problemas
2. Seleccionar un problema
   **Resultado esperado:** Se muestran los detalles completos del problema

---

### TC-005 – Ejecución de código simple

**Historia relacionada:** HU-005 - Escribir y Ejecutar Código
**Objetivo:** Validar que el código enviado se ejecute correctamente
**Datos de entrada:** Código: `print("Hello")`
**Pasos:**

1. Escribir código en el editor
2. Hacer clic en “Ejecutar”
   **Resultado esperado:** Se muestra “Hello” en consola

---

### TC-006 – Recompensa tras resolver un problema

**Historia relacionada:** HU-006 - Sistema de Recompensas
**Objetivo:** Verificar que se otorguen puntos y XP al resolver un problema
**Pasos:**

1. Resolver problema con código válido
2. Enviar solución
   **Resultado esperado:** Se suman puntos y aparece notificación

---

### TC-007 – Visualización del dashboard

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Validar que se muestra el progreso, puntos y ranking del usuario
**Pasos:**

1. Iniciar sesión
2. Acceder al dashboard
   **Resultado esperado:** Se visualiza progreso, medallas y ranking

---

### TC-008 – Soporte para múltiples lenguajes

**Historia relacionada:** HU-005 - Escribir y Ejecutar Código
**Objetivo:** Validar que la plataforma soporte varios lenguajes (Python, JS, C++, C#)
**Datos de entrada:** Código de ejemplo en cada lenguaje
**Pasos:**

1. Escribir código en el lenguaje elegido
2. Ejecutar
   **Resultado esperado:** Código ejecutado y resultado mostrado correctamente

---

### TC-009 – Confirmación de compras de recompensas

**Historia relacionada:** HU-006 - Sistema de Recompensas
**Objetivo:** Validar lógica de compra: requiere puntos suficientes y stock
**Pasos:**

1. Acceder a tienda
2. Intentar comprar recompensa
   **Resultado esperado:** Compra exitosa si cumple condiciones

---

### TC-010 – Activación de badges por condiciones

**Historia relacionada:** HU-006 - Sistema de Recompensas
**Objetivo:** Confirmar que al cumplir condiciones se otorga badge
**Pasos:**

1. Resolver problemas hasta cumplir condiciones
2. Revisar perfil
   **Resultado esperado:** Badge agregado correctamente

---

### TC-011 – Navbar nueva visible en todas las pantallas

**Historia relacionada:** Sin historia de usuario relacionada
**Objetivo:** Verificar visibilidad y funcionalidad del navbar en todo el sitio
**Pasos:**

1. Navegar por varias vistas
   **Resultado esperado:** Navbar visible y funcional en todas

---

### TC-012 – Tests corren dentro del mismo contenedor Docker

**Historia relacionada:** HU-005 - Escribir y Ejecutar Código
**Objetivo:** Validar ejecución de tests en el entorno dockerizado
**Pasos:**

1. Enviar código con pruebas
2. Ejecutar
   **Resultado esperado:** Tests se ejecutan dentro del mismo contenedor

---

### TC-013 – Renderizado del componente Leaderboard

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Verificar que el componente leaderboard se renderiza correctamente con sus encabezados
**Pasos:**

1. Iniciar sesión
2. Navegar al leaderboard
   **Resultado esperado:** Se muestra encabezado “Rank” y usuarios correctamente

---

### TC-014 – Simulación de usuario con useUser

**Historia relacionada:** HU-001 - Login de Usuario
**Objetivo:** Validar que el hook `useUser` simula correctamente un usuario autenticado
**Pasos:**

1. Mockear `useUser` en test
2. Renderizar componente dependiente
   **Resultado esperado:** Aparece nombre del usuario simulado

---

### TC-015 – Mock del componente UserProfileModal

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Aislar pruebas de leaderboard evitando el render real del modal
**Pasos:**

1. Mockear `UserProfileModal`
2. Renderizar leaderboard
   **Resultado esperado:** Se muestra placeholder del modal sin errores

---

### TC-016 – Simulación de fetch para leaderboard

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Validar render del leaderboard con datos simulados
**Pasos:**

1. Mockear fetch con usuarios
2. Renderizar leaderboard
   **Resultado esperado:** Usuarios simulados aparecen en la tabla

---

### TC-017 – Datos de leaderboard mostrados correctamente

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Confirmar que se renderizan correctamente nombres y datos
**Pasos:**

1. Cargar leaderboard con datos
   **Resultado esperado:** Aparecen usuarios como “Alice”, “Bob”, etc.

---

### TC-018 – Uso de temporizadores fake

**Historia relacionada:** Sin historia de usuario relacionada
**Objetivo:** Validar control de tiempo artificial para pruebas de animaciones o retrasos
**Pasos:**

1. Activar `vi.useFakeTimers()`
2. Ejecutar función temporizada
   **Resultado esperado:** Función ejecutada correctamente con avance manual del tiempo

---

### TC-019 – Limpieza de mocks entre pruebas

**Historia relacionada:** Sin historia de usuario relacionada
**Objetivo:** Confirmar que no hay mocks persistentes entre tests
**Pasos:**

1. Ejecutar varios tests
2. Verificar estado de mocks
   **Resultado esperado:** Todos los mocks son reiniciados entre pruebas

---

### TC-020 – Columna de nivel en leaderboard

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Validar que se muestra la columna de nivel de usuario correctamente
**Pasos:**

1. Renderizar leaderboard
   **Resultado esperado:** Se visualizan niveles como “100”, “90”, etc.

---

### TC-021 – Render sin errores con datos correctos

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Verificar estabilidad del render con props válidas
**Pasos:**

1. Renderizar leaderboard con datos válidos
   **Resultado esperado:** No hay errores o advertencias en consola

---

### TC-022 – Elementos esperados en el DOM

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Validar que todos los encabezados y nombres estén presentes
**Pasos:**

1. Renderizar leaderboard
   **Resultado esperado:** Todos los elementos clave son visibles

---

### TC-023 – Renderizado de Badge con texto

**Historia relacionada:** HU-006 - Sistema de Recompensas
**Objetivo:** Confirmar render correcto del texto de badge
**Pasos:**

1. Renderizar badge con prop `label="Fast Solver"`
   **Resultado esperado:** Texto “Fast Solver” visible en pantalla

---

### TC-024 – Componente de ejemplo muestra contenido

**Historia relacionada:** Sin historia de usuario relacionada
**Objetivo:** Validar visualización del contenido dummy de un componente demo
**Pasos:**

1. Renderizar componente
   **Resultado esperado:** Se muestra texto de demostración

---

### TC-025 – Spinner de carga visible durante carga

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Confirmar visualización del spinner cuando datos están cargando
**Pasos:**

1. Simular carga
   **Resultado esperado:** Spinner es visible en pantalla

---

### TC-026 – Render de página de privacidad

**Historia relacionada:** HU-002 - Ver contenido legal
**Objetivo:** Validar que la página muestra correctamente la política de privacidad
**Pasos:**

1. Ir a `/privacidad`
   **Resultado esperado:** Se muestra contenido legal actualizado

---

### TC-027 – Select funcional

**Historia relacionada:** HU-003 - Filtrar Problemas
**Objetivo:** Validar que se puede seleccionar opciones correctamente
**Pasos:**

1. Abrir select
2. Elegir opción
   **Resultado esperado:** Opción seleccionada se refleja en UI

---

### TC-028 – Tabla muestra filas con mock

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Confirmar render de tabla con filas de datos simulados
**Pasos:**

1. Renderizar tabla con mock
   **Resultado esperado:** Se muestran las filas esperadas

---

### TC-029 – Página de términos visible

**Historia relacionada:** HU-002 - Ver contenido legal
**Objetivo:** Verificar visualización del contenido legal de términos y condiciones
**Pasos:**

1. Ir a `/terminos`
   **Resultado esperado:** Todo el contenido está correctamente visible

---

### TC-030 – Cambio de tema claro/oscuro

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Confirmar que se alterna correctamente entre temas
**Pasos:**

1. Activar toggle de tema
   **Resultado esperado:** Tema cambia sin errores

---

### TC-031 – Toaster muestra notificaciones

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Validar que aparecen notificaciones tras eventos
**Pasos:**

1. Simular evento con éxito
   **Resultado esperado:** Aparece toast correspondiente

---

### TC-032 – Importación de componentes sin errores

**Historia relacionada:** Sin historia de usuario relacionada
**Objetivo:** Asegurar compatibilidad entre todos los componentes al renderizar juntos
**Pasos:**

1. Renderizar App con todos los componentes
   **Resultado esperado:** No hay errores ni conflictos

---

### TC-033 – Carga de página de inicio

**Historia relacionada:** HU-001 - Login de Usuario
**Objetivo:** Validar que la home se renderiza correctamente
**Pasos:**

1. Visitar `/`
   **Resultado esperado:** Página cargada exitosamente

---

### TC-034 – Navegación entre secciones

**Historia relacionada:** HU-001, HU-007
**Objetivo:** Validar funcionamiento de navegación básica
**Pasos:**

1. Usar navbar
2. Navegar a diferentes secciones
   **Resultado esperado:** Redirección correcta a cada vista

---

### TC-035 – Botón renderiza y responde

**Historia relacionada:** Sin historia de usuario relacionada
**Objetivo:** Confirmar render y funcionalidad básica de botones
**Pasos:**

1. Renderizar botón
2. Hacer clic
   **Resultado esperado:** Acción disparada correctamente

---

### TC-036 – Card muestra contenido hijo

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Verificar que el componente `Card` muestra correctamente contenido anidado
**Pasos:**

1. Renderizar card con children
   **Resultado esperado:** Contenido visible correctamente

---
Claro, aquí te dejo la última parte del diseño de casos de prueba, del **TC-037 al TC-052**, todos alineados con las **historias de usuario reales HU-001 a HU-007** cuando corresponde. Los que no tienen historia asociada se marcan como "Sin historia de usuario relacionada".

---

### TC-037 – Verificación de texto en card

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Validar que el texto contenido en una `Card` es renderizado correctamente
**Pasos:**

1. Renderizar `Card` con texto "Avance actual"
   **Resultado esperado:** Se visualiza el texto dentro del componente

---

### TC-038 – Interacción con toggle switch

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Verificar que el switch alterna correctamente entre estados
**Pasos:**

1. Renderizar componente con `Switch`
2. Hacer clic en el toggle
   **Resultado esperado:** Cambio de estado visible

---

### TC-039 – Componente de tabla renderiza headers

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Confirmar que los encabezados de la tabla se muestran correctamente
**Pasos:**

1. Renderizar tabla
   **Resultado esperado:** Se visualizan encabezados como “Usuario”, “Nivel”

---

### TC-040 – Renderización del modal de perfil

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Validar que el modal se abre y muestra la información del perfil
**Pasos:**

1. Clic en usuario en leaderboard
   **Resultado esperado:** Se abre modal con detalles del usuario

---

### TC-041 – Cierre del modal de perfil

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Verificar que el usuario puede cerrar el modal sin errores
**Pasos:**

1. Abrir modal
2. Clic en botón de cerrar
   **Resultado esperado:** El modal se oculta correctamente

---

### TC-042 – Componente `ProgressBar` muestra progreso

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Validar que la barra de progreso se actualiza según porcentaje
**Datos de entrada:** porcentaje: 75
**Pasos:**

1. Renderizar `ProgressBar`
   **Resultado esperado:** Se muestra visualmente el 75% de avance

---

### TC-043 – Resaltado de problemas resueltos

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Confirmar que los problemas ya resueltos aparecen marcados
**Pasos:**

1. Acceder a lista de problemas
2. Ver un problema ya resuelto
   **Resultado esperado:** Aparece con marca de "resuelto"

---

### TC-044 – Vista de resumen del perfil

**Historia relacionada:** HU-007 - Dashboard de Avances
**Objetivo:** Validar que el resumen del perfil muestra información clave
**Pasos:**

1. Ir a página de perfil
   **Resultado esperado:** Se muestra nombre, puntos, medallas

---

### TC-045 – Validación de inputs en el editor

**Historia relacionada:** HU-005 - Escribir y Ejecutar Código
**Objetivo:** Asegurar que el editor detecta código vacío o mal formado
**Datos de entrada:** (editor vacío)
**Pasos:**

1. Dejar el editor en blanco
2. Clic en “Ejecutar”
   **Resultado esperado:** Aparece mensaje de error indicando campo requerido

---

### TC-046 – Manejo de errores en ejecución de código

**Historia relacionada:** HU-005 - Escribir y Ejecutar Código
**Objetivo:** Verificar que errores en el código se manejan y muestran correctamente
**Datos de entrada:** Código inválido (por ejemplo, `prnt("Hola")`)
**Pasos:**

1. Escribir código con error
2. Ejecutar
   **Resultado esperado:** Se muestra mensaje de error del lenguaje correspondiente


### ✅ **TC-047 – Mission muestra nombre y icono**

**Fecha:** 13/06/2025
**Historia de usuario:** HU-007 – Dashboard de Avances
**Objetivo:** Verificar que el componente `Mission` renderiza correctamente el nombre y el ícono asociado
**Datos de entrada:** Misión con nombre `"Primer Desafío"` y `icon: "trophy"`
**Pasos:**

1. Renderizar componente `Mission` con props
2. Observar nombre e ícono
   **Resultado esperado:**

* El nombre `"Primer Desafío"` se visualiza
* El ícono de trofeo se renderiza correctamente

---

### ✅ **TC-048 – Función calcula puntos correctamente**

**Fecha:** 13/06/2025
**Historia de usuario:** HU-006 – Sistema de Recompensas
**Objetivo:** Verificar que la función `calculatePoints(difficulty)` retorna los puntos correctos
**Datos de entrada:** Dificultades: 1, 3, 5
**Pasos:**

1. Ejecutar función con cada dificultad
   **Resultado esperado:**

* Dificultad 1 → 10 puntos
* Dificultad 3 → 30 puntos
* Dificultad 5 → 50 puntos

---

### ✅ **TC-049 – Manejo correcto de estados true, false, null**

**Fecha:** 13/06/2025
**Historia de usuario:** HU-007 – Dashboard de Avances
**Objetivo:** Asegurar que el estado `status` en problemas se maneja correctamente para los tres casos
**Datos de entrada:** Problemas con `status = true`, `false`, `null`
**Pasos:**

1. Renderizar lista de problemas
2. Validar visualmente o con clase CSS el estado aplicado
   **Resultado esperado:**

* `true` → Aparece como resuelto
* `false` → No resuelto
* `null` → No intentado

---

### ✅ **TC-050 – Generación correcta de estrellas para dificultad**

**Fecha:** 13/06/2025
**Historia de usuario:** HU-004 – Asignación de Dificultad
**Objetivo:** Verificar que se generan estrellas según nivel de dificultad
**Datos de entrada:** Dificultad 1, 3, 5
**Pasos:**

1. Renderizar componente de dificultad
2. Contar estrellas
   **Resultado esperado:**

* Dificultad 1 → 1 estrella
* Dificultad 3 → 3 estrellas
* Dificultad 5 → 5 estrellas

---

### ✅ **TC-051 – Formato correcto para puntos**

**Fecha:** 13/06/2025
**Historia de usuario:** HU-007 – Dashboard de Avances
**Objetivo:** Verificar que los puntos se muestran en el formato correcto `"XX MC"`
**Datos de entrada:** Puntos: 10, 20, 35
**Pasos:**

1. Renderizar componente de puntuación
   **Resultado esperado:**

* Puntos 10 → `"10 MC"`
* Puntos 35 → `"35 MC"`

---

### ✅ **TC-052 – Testeo general de componentes con mock**

**Fecha:** 13/06/2025
**Historia de usuario:** HU-005 – Escribir y Ejecutar Código
**Objetivo:** Validar que los componentes principales se renderizan correctamente usando mocks
**Pasos:**

1. Mockear dependencias: `react-icons`, `lucide-react`
2. Renderizar componente principal (`ChallengeCard`, `Mission`, etc.)
   **Resultado esperado:**

* Componentes renderizados correctamente
* No se lanzan errores de importación
* Mocks se aplican correctamente

---

- ✅ **Pruebas automatizadas :**


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

