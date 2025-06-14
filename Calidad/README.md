# 4. Calidad (M5)

## Historias de Usuario: 
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

El plan de pruebas cubre los siguientes aspectos:
- Pruebas de desempeño: Se analizará la rapidez de respuesta del sistema.
- Pruebas de estrés: Se evaluará la capacidad de la plataforma bajo condiciones extremas.
- Pruebas de carga: Se medirá el rendimiento con múltiples usuarios simultáneos.
- Pruebas funcionales: Se validará el correcto funcionamiento de cada componente.
- Pruebas unitarias: Se probarán funciones individuales del sistema, sobretodo desde el lado del módulo de datos.
- Pruebas de aceptación: Se comprobará que la plataforma cumpla con los requisitos del usuario final.


---

### Pruebas de desempeño

| ID     | Nombre                         | Descripción                                                      | Criterios de Éxito                                      |
| ------ | ------------------------------ | ---------------------------------------------------------------- | ------------------------------------------------------- |
| PD-001 | Tiempo de respuesta del login  | Medir el tiempo que tarda el sistema en autenticar a un usuario. | La autenticación no debe tardar más de 3 segundos.      |
| PD-002 | Carga del dashboard            | Evaluar el tiempo de carga del dashboard.                        | El dashboard debe cargarse en menos de 4 segundos.      |
| PD-003 | Evaluación de código en Judge0 | Medir el tiempo de procesamiento del código en Judge0.           | La evaluación debe completarse en menos de 15 segundos. |

---

### Pruebas de estrés

| ID     | Nombre                                  | Descripción                                                                 | Criterios de Éxito                                           |
| ------ | --------------------------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------ |
| PE-001 | Uso de plataforma con mucha información | Cargar el dashboard de problemas cuando hay más de 100 en la base de datos. | La plataforma debe mantener tiempos de respuesta aceptables. |
| PE-002 | Envío masivo de código a Judge0         | Mandar varias solicitudes de evaluación en paralelo.                        | Judge0 debe seguir funcionando sin caídas abruptas.          |

---

### Pruebas de carga

| ID     | Nombre                                    | Descripción                                                             | Criterios de Éxito                                              |
| ------ | ----------------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------------------------- |
| PL-001 | Simulación de 5 usuarios registrados     | Medir el desempeño de la página cuando hay varios usuarios registrados. | La plataforma debe mantener tiempos de respuesta aceptables.    |
| PL-002 | Peticiones simultáneas a la base de datos | Enviar consultas masivas a PostgreSQL.                                  | La base de datos no debe ralentizarse significativamente.       |
| PL-003 | Simulación de 20 usuarios              | Enviar muchas solicitudes al servidor al mismo tiempo.                  | La plataforma no debe colapsar al enviar todas las solicitudes. |

---

### Pruebas Funcionales

| ID     | Nombre                              | Descripción                                                                                                 | Criterios de Éxito                                                                                                |
| ------ | ----------------------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| PF-001 | Autenticación de usuario            | Validar que los usuarios puedan iniciar sesión correctamente.                                               | El usuario debe autenticarse con credenciales válidas y recibir un mensaje de error si los datos son incorrectos. |
| PF-002 | Filtrado de problemas               | Comprobar que los filtros de dificultad y etiquetas funcionen correctamente.                                | La lista de problemas debe actualizarse dinámicamente al aplicar filtros y permitir eliminar filtros sin errores. |
| PF-003 | Evaluación de código                | Verificar que el código enviado a Judge0 se procese adecuadamente.                                          | Los resultados deben ser precisos y mostrarse correctamente al usuario.                                           |
| PF-004 | Registro de nuevos usuarios         | Validar que el sistema permita la creación de nuevas cuentas.                                               | El usuario debe recibir un correo de confirmación tras registrarse y poder iniciar sesión posteriormente.         |
| PF-005 | Envío de código                     | Comprobar que los usuarios puedan enviar sus soluciones de código correctamente.                            | La plataforma debe procesar y evaluar el código sin errores.                                                      |
| PF-006 | Generación de reportes de actividad | Validar que el sistema genere reportes sobre la actividad del usuario.                                      | Los reportes deben incluir número de problemas resueltos, XP ganado y estadísticas relevantes.                    |
| PF-007 | Historial de intentos               | Evaluar que los usuarios puedan consultar sus envíos anteriores de código.                                  | Los intentos deben mostrarse en orden cronológico con detalles del resultado de cada uno.                         |
| PF-008 | Respuesta a errores de ejecución    | Comprobar que el sistema muestre mensajes adecuados cuando el código presenta errores de sintaxis o lógica. | Los mensajes deben ser claros y ayudar al usuario a corregir el problema.                                         |

---

### Pruebas Unitarias

| ID     | Nombre                               | Descripción                                                                                                       | Criterios de Éxito                                                                                                  |
| ------ | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| PU-001 | Validación de datos de login         | Verificar que la función de validación de correo y contraseña funcione correctamente.                             | La función debe rechazar formatos de correo inválidos y contraseñas que no cumplan con los requisitos de seguridad. |
| PU-002 | Verificación de filtros              | Comprobar que las funciones de filtrado de problemas devuelvan los resultados esperados.                          | Los filtros deben retornar exactamente los problemas que cumplen con los criterios seleccionados.                   |
| PU-003 | Cálculo de recompensas               | Validar que el algoritmo de cálculo de XP y currency funcione según los parámetros establecidos.                  | Las recompensas deben calcularse correctamente según la dificultad del problema resuelto.                           |
| PU-004 | Integración con Judge0               | Comprobar que la función de envío de código a Judge0 funcione adecuadamente.                                      | La función debe establecer conexión con Judge0, enviar el código y recibir respuesta sin errores.                   |
| PU-005 | Análisis de código con SonarQube     | Verificar que la integración con SonarQube evalúe correctamente los estándares de calidad del código.             | SonarQube debe detectar problemas de calidad en el código y generar reportes precisos.                              |
| PU-006 | Actualización de progreso            | Validar que las funciones de actualización de estadísticas del usuario modifiquen correctamente la base de datos. | Los datos de progreso del usuario deben actualizarse de manera precisa en la base de datos.                         |
| PU-007 | Función de ordenamiento de problemas | Comprobar que la función para ordenar problemas por dificultad, fecha o popularidad funcione correctamente.       | Los problemas deben ordenarse según el criterio seleccionado sin excepción.                                         |
| PU-008 | Función de búsqueda                  | Verificar que la búsqueda de problemas por palabra clave funcione adecuadamente.                                  | La función debe retornar todos los problemas que contengan la palabra clave en su título o descripción.             |

---

### Pruebas de Aceptación

| ID     | Nombre                                       | Descripción                                                                                                                    | Criterios de Éxito                                                                                                                 |
| ------ | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------- |
| PA-001 | Registro con Google                          | Como usuario nuevo, quiero poder registrarme usando mi cuenta de Google para acceder rápidamente a la plataforma.              | El usuario puede registrarse con un solo clic utilizando su cuenta corporativa de Google y acceder inmediatamente a la plataforma. |
| PA-002 | Navegación intuitiva de problemas            | Como usuario, quiero navegar fácilmente por la lista de problemas disponibles para encontrar lo que necesito.                  | Los usuarios pueden filtrar, ordenar y buscar problemas sin dificultad y encuentran la información relevante en menos de 3 clics.  |
| PA-003 | Editor de código funcional                   | Como usuario, quiero un editor de código con resaltado de sintaxis y autocompletado para facilitar la escritura de soluciones. | El editor debe soportar múltiples lenguajes, tener resaltado de sintaxis y ofrecer sugerencias de autocompletado.                  |
| PA-004 | Retroalimentación clara sobre soluciones     | Como usuario, quiero recibir feedback detallado sobre mi código para entender por qué funciona o falla.                        | El sistema debe mostrar mensajes claros sobre errores de sintaxis, fallos en casos de prueba y sugerencias de mejora.              |
| PA-005 | Visualización de progreso                    | Como usuario, quiero ver mi progreso y compararlo con otros miembros del equipo para mantener la motivación.                   | El dashboard debe mostrar claramente estadísticas personales y comparativas con otros usuarios.                                    |
| PA-006 | Sistema de recompensas atractivo             | Como usuario, quiero recibir recompensas por resolver problemas para mantener mi interés en la plataforma.                     | Los usuarios deben recibir notificaciones visibles sobre las recompensas obtenidas y ver su acumulación en el perfil.              |
| PA-007 | Experiencia de usuario optimizada en móviles | Como usuario, quiero acceder a la plataforma desde mi dispositivo móvil para practicar en cualquier momento.                   | La interfaz debe ser responsiva y mantener todas sus funcionalidades en dispositivos móviles.                                      |
| PA-008 | Tiempo de respuesta satisfactorio            | Como usuario, espero que la plataforma responda rápidamente a mis interacciones para no perder tiempo esperando.               | Todas las operaciones básicas deben completarse en menos de 3 segundos y las evaluaciones de código en menos de 15 segundos.       |


Todas estas pruebas fueron validades de manera manual durante el desarrollo de nuestro código, y se presentaron avances a nuestros profesores para validar su uso. No son las pruebas que fueron automatizadas.

---

## Equipo de Calidad
Roles de cada miembro del equipo:
- Fernando Morán Fougerat: Validación de pruebas de estrés y unitarias.
- Imanol Armando González Solís: Validación de pruebas de carga.
- Rogelio Garza Rendón: Validación de pruebas funcionales
- Ramiro Alejandro Garza Villarreal: Validación de pruebas de aceptación y unitarias.


## Estándares aplicados 
Para este proyecto, estaremos siguiendo diferentes estándares para poder garantizar la calidad del software, usaremos los siguientes estándares:
- **ISO/IEC 25010** - Modelo de calidad del software que define características como funcionalidad, confiabilidad, usabilidad, eficiencia, mantenibilidad y portabilidad.
- **ISO/IEC 12207** - Estándar que establece procesos para el desarrollo y mantenimiento de software.
- **ISO/IEC 29119** - Establece procesos para el diseño, ejecución y documentación de pruebas.
- **ISO/IEC 9001** - Certifica que los procesos cumplen estándares de calidad internacionales. 
También estaremos incorporando niveles de modelos de gestión como por ejemplo:
- **CMMI - Nivel 3** - Los procesos estarán definidos y documentados durante todas las etapas del desarrollo, mejoras continuas mediante métricas de calidad y desempeño y usaremos práctica de gestión de riesgos y medición de calidad en el ciclo de vida del software.


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


### TC-047 – Mission muestra nombre y icono

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

### TC-048 – Función calcula puntos correctamente

**Fecha:** 13/06/2025
**Historia de usuario:** HU-006 – Sistema de Recompensas
**Objetivo:** Verificar que la función `calculatePoints(difficulty)` retorna los puntos correctos
**Datos de entrada:** Dificultades: 1, 3, 5
**Pasos:**

1. Ejecutar función con cada dificultad
   **Resultado esperado:**

* Dificultad 1 → 20 puntos
* Dificultad 3 → 60 puntos
* Dificultad 5 → 100 puntos

---

### TC-049 – Manejo correcto de estados true, false, null

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

### TC-050 – Generación correcta de estrellas para dificultad

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

### TC-051 – Formato correcto para puntos

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

### TC-052 – Testeo general de componentes con mock

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

## Plan de riesgos

### 1. Introducción

La gestión de riesgos es esencial para el éxito de cualquier proyecto de desarrollo de software. Un plan de riesgos bien estructurado nos permite anticipar y mitigar posibles problemas. A continuación, presentamos un plan de riesgos adaptado a un proyecto de desarrollo de software.

---

### 2. Identificación de Riesgos

Al momento de analizar los riesgos, usaremos las historias de usuario y exploramos posibles riesgos en cada etapa de desarrollo. Tomaremos en cuenta factores técnicos, como la estabilidad o la compatibilidad de tecnologías, así como los sistemas operativos, la disponibilidad de servicios externos y la integridad de los datos. Estaremos tomando en cuenta el impacto en la experiencia de usuario, asegurando que la plataforma sea accesible y funcional. A través de lluvia de ideas, revisión continua y búsqueda exhaustiva, identificaremos posibles riesgos, y definiremos estrategias para mitigarlos antes de que tengan un impacto en el proyecto.

| Clave   | Descripción                                                                                         |
|---------|---------------------------------------------------------------------------------------------------|
| RI-001  | El LLM que utilizamos se equivoca al modificar un problema                                        |
| RI-002  | Alguna dependencia no es compatible con las demás tecnologías que utilizamos                       |
| RI-003  | Inventario de la tienda inexacto                                                                  |
| RI-004  | Los usuarios no se sienten cómodos con la dificultad de los problemas                              |
| RI-005  | Sobrecarga de la plataforma por falta de recursos para mejorar el servidor                         |
| RI-006  | Algún servicio externo se cae durante la presentación al socio                                     |
| RI-007  | Error de precisión en alguna de las tags de un problema                                           |
| RI-008  | Cantidad de dinero digital inexacto                                                               |
| RI-009  | Se presenta algún bug en la tienda que impida a los usuarios redimir sus recompensas              |
| RI-010  | Corrupción de la base de datos debido a un error en el sistema de respaldo, afectando a todos los usuarios |
| RI-011  | Los problemas de programación no se refrescan correctamente, mostrando desafíos obsoletos o eliminados |
| RI-012  | Se elimina accidentalmente información en la base de datos                                        |
| RI-013  | Cierre forzado de la plataforma por problemas legales o de derechos de autor                      |
| RI-014  | Desincronización con Judge0, causando que el código enviado no se evalúe correctamente o tome demasiado tiempo |
| RI-015  | Ataque cibernético que tumbe el proyecto por completo                                             |
| RI-016  | Vulnerabilidades en dependencias de código                                                        |

---

### 3. Evaluación de Riesgos

#### Análisis de riesgos

| Clave  | Probabilidad             | Impacto        | Prioridad |
|--------|-------------------------|----------------|-----------|
| RI-001 | Muy Probable (5)        | Insignificante (1) | 5         |
| RI-002 | Muy Probable (5)        | Moderada (3)   | 15        |
| RI-003 | Probable (4)            | Menor (2)      | 8         |
| RI-004 | Probable (4)            | Moderada (3)   | 12        |
| RI-005 | Probable (4)            | Importante (4) | 16        |
| RI-006 | Probable (4)            | Catastrófica (5) | 20        |
| RI-007 | Posible (3)             | Insignificante (1) | 3         |
| RI-008 | Posible (3)             | Moderada (3)   | 9         |
| RI-009 | Posible (3)             | Importante (4) | 12        |
| RI-010 | Posible (3)             | Catastrófica (5) | 15        |
| RI-011 | No es probable (2)      | Moderada (3)   | 6         |
| RI-012 | No es probable (2)      | Importante (4) | 8         |
| RI-013 | No es probable (2)      | Catastrófica (5) | 10        |
| RI-014 | Muy improbable (1)      | Importante (4) | 4         |
| RI-015 | Muy improbable (1)      | Catastrófica (5) | 5         |
| RI-016 | Posible (2)             | Menor (3)      | 6         |

#### Clasificación de riesgos por nivel

- **Riesgo Bajo (Verde):**  
  RI-001, RI-007, RI-011, RI-014, RI-015, RI-016

- **Riesgo Medio (Amarillo):**  
  RI-003, RI-004, RI-008, RI-009, RI-012, RI-013

- **Riesgo Alto (Rojo):**  
  RI-002, RI-005, RI-006, RI-010


![image](https://github.com/user-attachments/assets/f57f990c-9ac5-4306-b105-56bf85c2a965)

---

### 4. Planificación de Estrategias de Mitigación

| Riesgo                         | Estrategias de mitigación                                                                                      |
|-------------------------------|----------------------------------------------------------------------------------------------------------------|
| **RI-001** El LLM se equivoca al modificar un problema | - Limitar el alcance de la LLM a tareas específicas (solo redacción).<br>- Revisión manual periódica.           |
| **RI-002** Dependencia incompatible                | - Pruebas de integración antes de implementar.<br>- Plan de contingencia para reemplazo.                       |
| **RI-003** Inventario inexacto                       | - Revisiones rutinarias.<br>- Sistema de colas para actualizaciones concurrentes.                              |
| **RI-004** Usuarios incómodos con dificultad        | - Filtrado por dificultad.<br>- Feedback continuo para ajustes.                                              |
| **RI-005** Sobrecarga por recursos insuficientes    | - Optimización de código y consultas.<br>- Pruebas de estrés periódicas.                                      |
| **RI-006** Caída de servicio externo                 | - Respaldo audiovisual (capturas, videos) para presentaciones.                                               |
| **RI-007** Error en tags de problema                  | - Permitir reportes de usuarios.<br>- Revisiones manuales periódicas.                                        |
| **RI-008** Dinero digital inexacto                    | - Sistema de respaldo para restaurar saldos.                                                                  |
| **RI-009** Bug que impida redención en tienda         | - Soporte preparado para resolver rápido.<br>- Ofrecer recompensas a usuarios afectados.                      |
| **RI-010** Corrupción base de datos                   | - Respaldos regulares.<br>- Monitoreo continuo.                                                               |
| **RI-011** Problemas no se refrescan correctamente    | - Caché con invalidación automática.<br>- Reportes de usuarios para problemas obsoletos.                      |
| **RI-012** Eliminación accidental en base de datos    | - Respaldos.<br>- Sistema de papelera de reciclaje.                                                           |
| **RI-013** Cierre por problemas legales               | - Equipo legal y cumplimiento normativo.<br>- Contenidos originales o con licencias.                          |
| **RI-014** Desincronización con Judge0                | - Servicio alternativo de evaluación.<br>- Reintentos automáticos.                                            |
| **RI-015** Ataque cibernético                           | - Medidas de seguridad robustas (encriptación, 2FA).<br>- Plan de respuesta a incidentes.                     |
| **RI-016** Vulnerabilidades en dependencias            | - Uso de dependencias confiables y actualizadas.<br>- Uso de lock files para versiones específicas.           |

---

### 5. Establecimiento de Medidas de Control

- **Seguimiento continuo:** Monitoreo periódico de sistemas y procesos clave durante 2 meses para detectar señales tempranas.  
- **Registro y revisión de logs y auditorías:** Auditorías de seguridad y análisis para detectar anomalías.  
- **Pruebas regulares:** Estrés, integración y pruebas unitarias para evaluar estabilidad.  
- **Mantenimiento de dependencias:** Revisión y actualización constante para minimizar vulnerabilidades.  
- **Evaluación de rendimiento:** Análisis de carga para prevenir problemas de escalabilidad.  
- **Estrategia de mitigación de incidentes:** Planes de acción para responder rápidamente ante incidentes.  

---

### 6. Comunicación y Colaboración

Durante el proyecto se fomentará una comunicación abierta para gestionar los riesgos de manera efectiva:

- **Comunicación con socio formador:** Reportes regulares y discusión de riesgos y soluciones.  
- **Documentación:** Registro detallado de riesgos, mitigaciones y respuestas.  
- **Feedback:** Retroalimentación continua del equipo para mejorar gestión de riesgos.  

---

## Reporte de uso SonarQube

- Integrado como herramienta de análisis estático de código.
- Se ejecutaron escaneos para:
  - Detectar código duplicado.
  - Promover el uso de buenas prácticas.
  - Identificar posibles vulnerabilidades o malas implementaciones.
- Se resolvieron advertencias relacionadas con la legibilidad, estructura y calidad general del código.


Fotos de analísis de código con SonarQube:

![Captura de pantalla 2025-06-13 190402](https://github.com/user-attachments/assets/8facb9b3-5c70-46fc-8da4-59bd8bcc2a59)

![Captura de pantalla 2025-06-13 190237](https://github.com/user-attachments/assets/cf07c4c2-0eef-41cc-a9e7-73e7909c4195)


Dificultades encontradas:

No logramos correctamente unir dentro de nuestro análisis con SonarQube el Coverage de líneas que testeamos automáticamente, por lo cual no salía dentro de nuestro análisis presente. A pesar de esto, nuestro testeo manual y automatizado, evitar duplicación de código y buenas practicas aseguran una alta calidad en nuestro código entregado.
