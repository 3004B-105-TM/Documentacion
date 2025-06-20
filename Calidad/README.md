# Calidad (M5)

## Índice

- [1. Historias de Usuario con Caso de Uso](#historias-de-usuario)
- [2. Plan de pruebas](#plan-de-pruebas)
- [2.1 Diseño de pruebas](#diseño-de-pruebas)
- [2.2 Limitaciones en el alcance de las pruebas](#limitaciones-en-el-alcance-de-las-pruebas)
- [2.3 Pruebas de desempeño](#pruebas-de-desempeño)
- [2.4 Pruebas de estrés](#pruebas-de-estrés)
- [2.5 Pruebas de carga](#pruebas-de-carga)
- [2.6 Pruebas funcionales](#pruebas-funcionales)
- [2.7 Pruebas unitarias](#pruebas-unitarias)
- [2.8 Pruebas de aceptación](#pruebas-de-aceptación)
- [3. Pruebas Automatizadas con Vitest, Jest, Cypress](#pruebas-automatizadas-con-vitest-jest-cypress)
- [3.1 Bitacora de pruebas](#bitacora-de-pruebas)
- [4. Equipo de Calidad](#equipo-de-calidad)
- [5. Estándares aplicados](#estándares-aplicados)
- [6. Plan de riesgos](#plan-de-riesgos)
- [7. Reporte de uso SonarQube](#reporte-de-uso-sonarqube)
- [8. Referencias](#referencias)

## Historias de Usuario:

Se puede ver funcionales en video demo.

#### HU-001 - Login de Usuario

**Descripción:** Como usuario y trabajador de la empresa, quiero poder ingresar a la plataforma.  
**Criterios de Aceptación:**

- Ingreso con correo y contraseña.
- Permitir uso de cuenta Google para mayor velocidad.
- Mensaje de error si son incorrectos o inválidos.

**Caso de uso**

## ![image](https://github.com/user-attachments/assets/f4a9411d-d099-47b1-ad77-9a9666beb910)

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

**Descripción:** Como usuario, quiero recibir XP y puntos al resolver problemas.  
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

### Diseño de pruebas

El plan de pruebas cubre los siguientes aspectos:

- Pruebas de desempeño: Se analizará la rapidez de respuesta del sistema.
- Pruebas de estrés: Se evaluará la capacidad de la plataforma bajo condiciones extremas.
- Pruebas de carga: Se medirá el rendimiento con múltiples usuarios simultáneos.
- Pruebas funcionales: Se validará el correcto funcionamiento de cada componente.
- Pruebas unitarias: Se probarán funciones individuales del sistema, sobretodo desde el lado del módulo de datos.
- Pruebas de aceptación: Se comprobará que la plataforma cumpla con los requisitos del usuario final.

---

### Limitaciones en el alcance de las pruebas

Debido a restricciones de tiempo y recursos, no se contempla la cobertura total de todas las áreas de prueba. Si bien reconocemos la importancia de validar el uso eficiente de recursos, realizar pruebas de carga con un número alto de usuarios concurrentes (por ejemplo, ~1000) podría sobrepasar la capacidad actual de nuestra máquina virtual y base de datos.

No obstante, mitigamos este riesgo mediante técnicas de troubleshooting y monitoreo del consumo durante la ejecución del sistema, como la implementación de procesos en single drop, controlando explícitamente la asignación de recursos por instancia.

Adicionalmente, las pruebas actuales no contemplan casos de uso con usuarios que empleen distintos lenguajes, dado el bajo impacto previsto en esta etapa y el tiempo limitado para entrega. Sin embargo, esta funcionalidad sería una mejora valiosa para una futura versión en producción.

---

### Pruebas de desempeño

| ID     | Nombre                         | Descripción                                                      | Criterios de Éxito                                      |
| ------ | ------------------------------ | ---------------------------------------------------------------- | ------------------------------------------------------- |
| PD-001 | Tiempo de respuesta del login  | Medir el tiempo que tarda el sistema en autenticar a un usuario. | La autenticación no debe tardar más de 3 segundos.      |
| PD-002 | Carga del dashboard            | Evaluar el tiempo de carga del dashboard.                        | El dashboard debe cargarse en menos de 4 segundos.      |
| PD-003 | Evaluación de código en Docker | Medir el tiempo de procesamiento del código en Docker.           | La evaluación debe completarse en menos de 15 segundos. |

---

### Pruebas de estrés

| ID     | Nombre                                  | Descripción                                                                 | Criterios de Éxito                                           |
| ------ | --------------------------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------ |
| PE-001 | Uso de plataforma con mucha información | Cargar el dashboard de problemas cuando hay más de 100 en la base de datos. | La plataforma debe mantener tiempos de respuesta aceptables. |
| PE-002 | Envío masivo de código a Docker         | Mandar varias solicitudes de evaluación en paralelo.                        | Docker debe seguir funcionando sin caídas abruptas.          |

---

### Pruebas de carga

| ID     | Nombre                                    | Descripción                                                             | Criterios de Éxito                                              |
| ------ | ----------------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------------------------- |
| PL-001 | Simulación de 5 usuarios registrados      | Medir el desempeño de la página cuando hay varios usuarios registrados. | La plataforma debe mantener tiempos de respuesta aceptables.    |
| PL-002 | Peticiones simultáneas a la base de datos | Enviar consultas masivas a PostgreSQL.                                  | La base de datos no debe ralentizarse significativamente.       |
| PL-003 | Simulación de 20 usuarios                 | Enviar muchas solicitudes al servidor al mismo tiempo.                  | La plataforma no debe colapsar al enviar todas las solicitudes. |

---

### Pruebas Funcionales

| ID     | Nombre                              | Descripción                                                                                                 | Criterios de Éxito                                                                                                |
| ------ | ----------------------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| PF-001 | Autenticación de usuario            | Validar que los usuarios puedan iniciar sesión correctamente.                                               | El usuario debe autenticarse con credenciales válidas y recibir un mensaje de error si los datos son incorrectos. |
| PF-002 | Filtrado de problemas               | Comprobar que los filtros de dificultad y etiquetas funcionen correctamente.                                | La lista de problemas debe actualizarse dinámicamente al aplicar filtros y permitir eliminar filtros sin errores. |
| PF-003 | Evaluación de código                | Verificar que el código enviado a Backend se procese adecuadamente.                                          | Los resultados deben ser precisos y mostrarse correctamente al usuario.                                           |
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
| PU-004 | Integración con Backend               | Comprobar que la función de envío de código a Backend funcione adecuadamente.                                      | La función debe establecer conexión con Backend, enviar el código y recibir respuesta sin errores.                   |
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

---

Todas estas pruebas fueron validades de manera manual durante el desarrollo de nuestro código, y se presentaron avances a nuestros profesores para validar su uso. No son las pruebas que fueron automatizadas.

---

## Pruebas Automatizadas con Vitest, Jest, Cypress

Para ver archivos tests, ver carpeta en test en front end para ver fotos de ejecución en terminal, esta en carpeta tests.

### TC-001 – Redirección tras login exitoso

- **Historia relacionada:** HU-001 - Login de Usuario
- **Objetivo:** Validar que el usuario autenticado sea redirigido al dashboard.
**Datos de entrada:** Email: [user@empresa.com](mailto:user@empresa.com), Contraseña: correcta123
- **Pasos:**

1. Ir al formulario de login
2. Ingresar correo y contraseña válidos
3. Hacer clic en “Iniciar sesión”
   **Resultado esperado:** Usuario es redirigido al dashboard

---

### TC-002 – Login con credenciales inválidas

- **Historia relacionada:** HU-001 - Login de Usuario
- **Objetivo:** Validar que se muestre un mensaje de error al ingresar credenciales incorrectas.
**Datos de entrada:** Email: [falso@mail.com](mailto:falso@mail.com), Contraseña: error123
- **Pasos:**

1. Ir al login
2. Ingresar datos inválidos
3. Hacer clic en “Iniciar sesión”
   **Resultado esperado:** Se muestra alerta de credenciales incorrectas

---

### TC-003 – Filtro por dificultad “Difícil”

- **Historia relacionada:** HU-003 - Filtrar Problemas
- **Objetivo:** Validar que solo se muestren problemas difíciles al aplicar ese filtro.
**Datos de entrada:** Dificultad: Difícil
- **Pasos:**

1. Ir a sección de problemas
2. Seleccionar filtro “Difícil”
   **Resultado esperado:** Lista contiene únicamente problemas difíciles

---

### TC-004 – Ver detalles de un problema

- **Historia relacionada:** HU-004 - Ver Detalles del Problema
- **Objetivo:** Validar que se muestra título, descripción y ejemplos al abrir un problema
- **Pasos:**

1. Ir a lista de problemas
2. Seleccionar un problema
   **Resultado esperado:** Se muestran los detalles completos del problema

---

### TC-005 – Ejecución de código simple

- **Historia relacionada:** HU-005 - Escribir y Ejecutar Código
- **Objetivo:** Validar que el código enviado se ejecute correctamente
**Datos de entrada:** Código: `print("Hello")`
- **Pasos:**

1. Escribir código en el editor
2. Hacer clic en “Ejecutar”
   **Resultado esperado:** Se muestra “Hello” en consola

---

### TC-006 – Recompensa tras resolver un problema

- **Historia relacionada:** HU-006 - Sistema de Recompensas
- **Objetivo:** Verificar que se otorguen puntos y XP al resolver un problema
- **Pasos:**

1. Resolver problema con código válido
2. Enviar solución
   **Resultado esperado:** Se suman puntos y aparece notificación

---

### TC-007 – Visualización del dashboard

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Validar que se muestra el progreso, puntos y ranking del usuario
- **Pasos:**

1. Iniciar sesión
2. Acceder al dashboard
   **Resultado esperado:** Se visualiza progreso, medallas y ranking

---

### TC-008 – Soporte para múltiples lenguajes

- **Historia relacionada:** HU-005 - Escribir y Ejecutar Código
- **Objetivo:** Validar que la plataforma soporte varios lenguajes (Python, JS, C++, C#)
**Datos de entrada:** Código de ejemplo en cada lenguaje
- **Pasos:**

1. Escribir código en el lenguaje elegido
2. Ejecutar
   **Resultado esperado:** Código ejecutado y resultado mostrado correctamente

---

### TC-009 – Confirmación de compras de recompensas

- **Historia relacionada:** HU-006 - Sistema de Recompensas
- **Objetivo:** Validar lógica de compra: requiere puntos suficientes y stock
- **Pasos:**

1. Acceder a tienda
2. Intentar comprar recompensa
   **Resultado esperado:** Compra exitosa si cumple condiciones

---

### TC-010 – Activación de badges por condiciones

- **Historia relacionada:** HU-006 - Sistema de Recompensas
- **Objetivo:** Confirmar que al cumplir condiciones se otorga badge
- **Pasos:**

1. Resolver problemas hasta cumplir condiciones
2. Revisar perfil
   **Resultado esperado:** Badge agregado correctamente

---

### TC-011 – Navbar nueva visible en todas las pantallas

- **Historia relacionada:** Sin historia de usuario relacionada
- **Objetivo:** Verificar visibilidad y funcionalidad del navbar en todo el sitio
- **Pasos:**

1. Navegar por varias vistas
   **Resultado esperado:** Navbar visible y funcional en todas

---

### TC-012 – Tests corren dentro del mismo contenedor Docker

- **Historia relacionada:** HU-005 - Escribir y Ejecutar Código
- **Objetivo:** Validar ejecución de tests en el entorno dockerizado
- **Pasos:**

1. Enviar código con pruebas
2. Ejecutar
   **Resultado esperado:** Tests se ejecutan dentro del mismo contenedor

---

### TC-013 – Renderizado del componente Leaderboard

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Verificar que el componente leaderboard se renderiza correctamente con sus encabezados
- **Pasos:**

1. Iniciar sesión
2. Navegar al leaderboard
   **Resultado esperado:** Se muestra encabezado “Rank” y usuarios correctamente

---

### TC-014 – Simulación de usuario con useUser

- **Historia relacionada:** HU-001 - Login de Usuario
- **Objetivo:** Validar que el hook `useUser` simula correctamente un usuario autenticado
- **Pasos:**

1. Mockear `useUser` en test
2. Renderizar componente dependiente
   **Resultado esperado:** Aparece nombre del usuario simulado

---

### TC-015 – Mock del componente UserProfileModal

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Aislar pruebas de leaderboard evitando el render real del modal
- **Pasos:**

1. Mockear `UserProfileModal`
2. Renderizar leaderboard
   **Resultado esperado:** Se muestra placeholder del modal sin errores

---

### TC-016 – Simulación de fetch para leaderboard

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Validar render del leaderboard con datos simulados
- **Pasos:**

1. Mockear fetch con usuarios
2. Renderizar leaderboard
   **Resultado esperado:** Usuarios simulados aparecen en la tabla

---

### TC-017 – Datos de leaderboard mostrados correctamente

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Confirmar que se renderizan correctamente nombres y datos
- **Pasos:**

1. Cargar leaderboard con datos
   **Resultado esperado:** Aparecen usuarios como “Alice”, “Bob”, etc.

---

### TC-018 – Uso de temporizadores fake

- **Historia relacionada:** Sin historia de usuario relacionada
- **Objetivo:** Validar control de tiempo artificial para pruebas de animaciones o retrasos
- **Pasos:**

1. Activar `vi.useFakeTimers()`
2. Ejecutar función temporizada
   **Resultado esperado:** Función ejecutada correctamente con avance manual del tiempo

---

### TC-019 – Limpieza de mocks entre pruebas

- **Historia relacionada:** Sin historia de usuario relacionada
- **Objetivo:** Confirmar que no hay mocks persistentes entre tests
- **Pasos:**

1. Ejecutar varios tests
2. Verificar estado de mocks
   **Resultado esperado:** Todos los mocks son reiniciados entre pruebas

---

### TC-020 – Columna de nivel en leaderboard

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Validar que se muestra la columna de nivel de usuario correctamente
- **Pasos:**

1. Renderizar leaderboard
   **Resultado esperado:** Se visualizan niveles como “100”, “90”, etc.

---

### TC-021 – Render sin errores con datos correctos

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Verificar estabilidad del render con props válidas
- **Pasos:**

1. Renderizar leaderboard con datos válidos
   **Resultado esperado:** No hay errores o advertencias en consola

---

### TC-022 – Elementos esperados en el DOM

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Validar que todos los encabezados y nombres estén presentes
- **Pasos:**

1. Renderizar leaderboard
   **Resultado esperado:** Todos los elementos clave son visibles

---

### TC-023 – Renderizado de Badge con texto

- **Historia relacionada:** HU-006 - Sistema de Recompensas
- **Objetivo:** Confirmar render correcto del texto de badge
- **Pasos:**

1. Renderizar badge con prop `label="Fast Solver"`
   **Resultado esperado:** Texto “Fast Solver” visible en pantalla

---

### TC-024 – Componente de ejemplo muestra contenido

- **Historia relacionada:** Sin historia de usuario relacionada
- **Objetivo:** Validar visualización del contenido dummy de un componente demo
- **Pasos:**

1. Renderizar componente
   **Resultado esperado:** Se muestra texto de demostración

---

### TC-025 – Spinner de carga visible durante carga

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Confirmar visualización del spinner cuando datos están cargando
- **Pasos:**

1. Simular carga
   **Resultado esperado:** Spinner es visible en pantalla

---

### TC-026 – Render de página de privacidad

- **Historia relacionada:** HU-002 - Ver contenido legal
- **Objetivo:** Validar que la página muestra correctamente la política de privacidad
- **Pasos:**

1. Ir a `/privacidad`
   **Resultado esperado:** Se muestra contenido legal actualizado

---

### TC-027 – Select funcional

- **Historia relacionada:** HU-003 - Filtrar Problemas
- **Objetivo:** Validar que se puede seleccionar opciones correctamente
- **Pasos:**

1. Abrir select
2. Elegir opción
   **Resultado esperado:** Opción seleccionada se refleja en UI

---

### TC-028 – Tabla muestra filas con mock

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Confirmar render de tabla con filas de datos simulados
- **Pasos:**

1. Renderizar tabla con mock
   **Resultado esperado:** Se muestran las filas esperadas

---

### TC-029 – Página de términos visible

- **Historia relacionada:** HU-002 - Ver contenido legal
- **Objetivo:** Verificar visualización del contenido legal de términos y condiciones
- **Pasos:**

1. Ir a `/terminos`
   **Resultado esperado:** Todo el contenido está correctamente visible

---

### TC-030 – Cambio de tema claro/oscuro

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Confirmar que se alterna correctamente entre temas
- **Pasos:**

1. Activar toggle de tema
   **Resultado esperado:** Tema cambia sin errores

---

### TC-031 – Toaster muestra notificaciones

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Validar que aparecen notificaciones tras eventos
- **Pasos:**

1. Simular evento con éxito
   **Resultado esperado:** Aparece toast correspondiente

---

### TC-032 – Importación de componentes sin errores

- **Historia relacionada:** Sin historia de usuario relacionada
- **Objetivo:** Asegurar compatibilidad entre todos los componentes al renderizar juntos
- **Pasos:**

1. Renderizar App con todos los componentes
   **Resultado esperado:** No hay errores ni conflictos

---

### TC-033 – Carga de página de inicio

- **Historia relacionada:** HU-001 - Login de Usuario
- **Objetivo:** Validar que la home se renderiza correctamente
- **Pasos:**

1. Visitar `/`
   **Resultado esperado:** Página cargada exitosamente

---

### TC-034 – Navegación entre secciones

- **Historia relacionada:** HU-001, HU-007
- **Objetivo:** Validar funcionamiento de navegación básica
- **Pasos:**

1. Usar navbar
2. Navegar a diferentes secciones
   **Resultado esperado:** Redirección correcta a cada vista

---

### TC-035 – Botón renderiza y responde

- **Historia relacionada:** Sin historia de usuario relacionada
- **Objetivo:** Confirmar render y funcionalidad básica de botones
- **Pasos:**

1. Renderizar botón
2. Hacer clic
   **Resultado esperado:** Acción disparada correctamente

---

### TC-036 – Card muestra contenido hijo

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Verificar que el componente `Card` muestra correctamente contenido anidado
- **Pasos:**

1. Renderizar card con children
   **Resultado esperado:** Contenido visible correctamente

---

### TC-037 – Verificación de texto en card

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Validar que el texto contenido en una `Card` es renderizado correctamente
- **Pasos:**

1. Renderizar `Card` con texto "Avance actual"
   **Resultado esperado:** Se visualiza el texto dentro del componente

---

### TC-038 – Interacción con toggle switch

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Verificar que el switch alterna correctamente entre estados
- **Pasos:**

1. Renderizar componente con `Switch`
2. Hacer clic en el toggle
   **Resultado esperado:** Cambio de estado visible

---

### TC-039 – Componente de tabla renderiza headers

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Confirmar que los encabezados de la tabla se muestran correctamente
- **Pasos:**

1. Renderizar tabla
   **Resultado esperado:** Se visualizan encabezados como “Usuario”, “Nivel”

---

### TC-040 – Renderización del modal de perfil

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Validar que el modal se abre y muestra la información del perfil
- **Pasos:**

1. Clic en usuario en leaderboard
   **Resultado esperado:** Se abre modal con detalles del usuario

---

### TC-041 – Cierre del modal de perfil

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Verificar que el usuario puede cerrar el modal sin errores
- **Pasos:**

1. Abrir modal
2. Clic en botón de cerrar
   **Resultado esperado:** El modal se oculta correctamente

---

### TC-042 – Componente `ProgressBar` muestra progreso

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Validar que la barra de progreso se actualiza según porcentaje
**Datos de entrada:** porcentaje: 75
- **Pasos:**

1. Renderizar `ProgressBar`
   **Resultado esperado:** Se muestra visualmente el 75% de avance

---

### TC-043 – Resaltado de problemas resueltos

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Confirmar que los problemas ya resueltos aparecen marcados
- **Pasos:**

1. Acceder a lista de problemas
2. Ver un problema ya resuelto
   **Resultado esperado:** Aparece con marca de "resuelto"

---

### TC-044 – Vista de resumen del perfil

- **Historia relacionada:** HU-007 - Dashboard de Avances
- **Objetivo:** Validar que el resumen del perfil muestra información clave
- **Pasos:**

1. Ir a página de perfil
   **Resultado esperado:** Se muestra nombre, puntos, medallas

---

### TC-045 – Validación de inputs en el editor

- **Historia relacionada:** HU-005 - Escribir y Ejecutar Código
- **Objetivo:** Asegurar que el editor detecta código vacío o mal formado
**Datos de entrada:** (editor vacío)
- **Pasos:**

1. Dejar el editor en blanco
2. Clic en “Ejecutar”
   **Resultado esperado:** Aparece mensaje de error indicando campo requerido

---

### TC-046 – Manejo de errores en ejecución de código

- **Historia relacionada:** HU-005 - Escribir y Ejecutar Código
- **Objetivo:** Verificar que errores en el código se manejan y muestran correctamente
**Datos de entrada:** Código inválido (por ejemplo, `prnt("Hola")`)
- **Pasos:**

1. Escribir código con error
2. Ejecutar
   **Resultado esperado:** Se muestra mensaje de error del lenguaje correspondiente

### TC-047 – Mission muestra nombre y icono

**Fecha:** 13/06/2025
**Historia de usuario:** HU-007 – Dashboard de Avances
- **Objetivo:** Verificar que el componente `Mission` renderiza correctamente el nombre y el ícono asociado
**Datos de entrada:** Misión con nombre `"Primer Desafío"` y `icon: "trophy"`
- **Pasos:**

1. Renderizar componente `Mission` con props
2. Observar nombre e ícono
   **Resultado esperado:**

- El nombre `"Primer Desafío"` se visualiza
- El ícono de trofeo se renderiza correctamente

---

### TC-048 – Función calcula puntos correctamente

**Fecha:** 13/06/2025
**Historia de usuario:** HU-006 – Sistema de Recompensas
- **Objetivo:** Verificar que la función `calculatePoints(difficulty)` retorna los puntos correctos
**Datos de entrada:** Dificultades: 1, 3, 5
- **Pasos:**

1. Ejecutar función con cada dificultad
   **Resultado esperado:**

- Dificultad 1 → 20 puntos
- Dificultad 3 → 60 puntos
- Dificultad 5 → 100 puntos

---

### TC-049 – Manejo correcto de estados true, false, null

**Fecha:** 13/06/2025
**Historia de usuario:** HU-007 – Dashboard de Avances
- **Objetivo:** Asegurar que el estado `status` en problemas se maneja correctamente para los tres casos
**Datos de entrada:** Problemas con `status = true`, `false`, `null`
- **Pasos:**

1. Renderizar lista de problemas
2. Validar visualmente o con clase CSS el estado aplicado
   **Resultado esperado:**

- `true` → Aparece como resuelto
- `false` → No resuelto
- `null` → No intentado

---

### TC-050 – Generación correcta de estrellas para dificultad

**Fecha:** 13/06/2025
**Historia de usuario:** HU-004 – Asignación de Dificultad
- **Objetivo:** Verificar que se generan estrellas según nivel de dificultad
**Datos de entrada:** Dificultad 1, 3, 5
- **Pasos:**

1. Renderizar componente de dificultad
2. Contar estrellas
   **Resultado esperado:**

- Dificultad 1 → 1 estrella
- Dificultad 3 → 3 estrellas
- Dificultad 5 → 5 estrellas

---

### TC-051 – Formato correcto para puntos

**Fecha:** 13/06/2025
**Historia de usuario:** HU-007 – Dashboard de Avances
- **Objetivo:** Verificar que los puntos se muestran en el formato correcto `"XX MC"`
**Datos de entrada:** Puntos: 10, 20, 35
- **Pasos:**

1. Renderizar componente de puntuación
   **Resultado esperado:**

- Puntos 10 → `"10 MC"`
- Puntos 35 → `"35 MC"`

---

### TC-052 – Testeo general de componentes con mock

**Fecha:** 13/06/2025
**Historia de usuario:** HU-005 – Escribir y Ejecutar Código
- **Objetivo:** Validar que los componentes principales se renderizan correctamente usando mocks
- **Pasos:**

1. Mockear dependencias: `react-icons`, `lucide-react`
2. Renderizar componente principal (`ChallengeCard`, `Mission`, etc.)
   **Resultado esperado:**

- Componentes renderizados correctamente
- No se lanzan errores de importación
- Mocks se aplican correctamente

---

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

## Equipo de Calidad

Roles de cada miembro del equipo:

- Fernando Morán Fougerat: Validación de pruebas de estrés y unitarias.
- Imanol Armando González Solís: Validación de pruebas de carga.
- Rogelio Garza Rendón: Validación de pruebas funcionales
- Ramiro Alejandro Garza Villarreal: Validación de pruebas de aceptación y unitarias.
- Diego Dávila: Validación general.

## Estándares aplicados

Para este proyecto, estaremos siguiendo diferentes estándares para poder garantizar la calidad del software, usaremos los siguientes estándares:

- **ISO/IEC 25010** - Modelo de calidad del software que define características como funcionalidad, confiabilidad, usabilidad, eficiencia, mantenibilidad y portabilidad.
- **ISO/IEC 12207** - Estándar que establece procesos para el desarrollo y mantenimiento de software.
- **ISO/IEC 29119** - Establece procesos para el diseño, ejecución y documentación de pruebas.
- **ISO/IEC 9001** - Certifica que los procesos cumplen estándares de calidad internacionales.
  También estaremos incorporando niveles de modelos de gestión como por ejemplo:
- **CMMI - Nivel 3** - Los procesos estarán definidos y documentados durante todas las etapas del desarrollo, mejoras continuas mediante métricas de calidad y desempeño y usaremos práctica de gestión de riesgos y medición de calidad en el ciclo de vida del software.

---

## Plan de riesgos

### 1. Introducción

La gestión de riesgos es esencial para el éxito de cualquier proyecto de desarrollo de software. Un plan de riesgos bien estructurado nos permite anticipar y mitigar posibles problemas.

---

### 2. Identificación de Riesgos

Al momento de analizar los riesgos, usaremos las historias de usuario y exploramos posibles riesgos en cada etapa de desarrollo. Tomaremos en cuenta factores técnicos, como la estabilidad o la compatibilidad de tecnologías, así como los sistemas operativos, la disponibilidad de servicios externos y la integridad de los datos. Estaremos tomando en cuenta el impacto en la experiencia de usuario, asegurando que la plataforma sea accesible y funcional. A través de lluvia de ideas, revisión continua y búsqueda exhaustiva, identificaremos posibles riesgos, y definiremos estrategias para mitigarlos antes de que tengan un impacto en el proyecto.

| Clave  | Descripción                                                                                                    |
| ------ | -------------------------------------------------------------------------------------------------------------- |
| RI-001 | El LLM que utilizamos se equivoca al modificar un problema                                                     |
| RI-002 | Alguna dependencia no es compatible con las demás tecnologías que utilizamos                                   |
| RI-003 | Inventario de la tienda inexacto                                                                               |
| RI-004 | Los usuarios no se sienten cómodos con la dificultad de los problemas                                          |
| RI-005 | Sobrecarga de la plataforma por falta de recursos para mejorar el servidor                                     |
| RI-006 | Algún servicio externo se cae durante la presentación al socio                                                 |
| RI-007 | Error de precisión en alguna de las tags de un problema                                                        |
| RI-008 | Cantidad de dinero digital inexacto                                                                            |
| RI-009 | Se presenta algún bug en la tienda que impida a los usuarios redimir sus recompensas                           |
| RI-010 | Corrupción de la base de datos debido a un error en el sistema de respaldo, afectando a todos los usuarios     |
| RI-011 | Los problemas de programación no se refrescan correctamente, mostrando desafíos obsoletos o eliminados         |
| RI-012 | Se elimina accidentalmente información en la base de datos                                                     |
| RI-013 | Cierre forzado de la plataforma por problemas legales o de derechos de autor                                   |
| RI-014 | Desincronización con Docker, causando que el código enviado no se evalúe correctamente o tome demasiado tiempo |
| RI-015 | Ataque cibernético que tumbe el proyecto por completo                                                          |
| RI-016 | Vulnerabilidades en dependencias de código                                                                     |

---

### 3. Evaluación de Riesgos

#### Análisis de riesgos

| Clave  | Probabilidad       | Impacto            | Prioridad |
| ------ | ------------------ | ------------------ | --------- |
| RI-001 | Muy Probable (5)   | Insignificante (1) | 5         |
| RI-002 | Muy Probable (5)   | Moderada (3)       | 15        |
| RI-003 | Probable (4)       | Menor (2)          | 8         |
| RI-004 | Probable (4)       | Moderada (3)       | 12        |
| RI-005 | Probable (4)       | Importante (4)     | 16        |
| RI-006 | Probable (4)       | Catastrófica (5)   | 20        |
| RI-007 | Posible (3)        | Insignificante (1) | 3         |
| RI-008 | Posible (3)        | Moderada (3)       | 9         |
| RI-009 | Posible (3)        | Importante (4)     | 12        |
| RI-010 | Posible (3)        | Catastrófica (5)   | 15        |
| RI-011 | No es probable (2) | Moderada (3)       | 6         |
| RI-012 | No es probable (2) | Importante (4)     | 8         |
| RI-013 | No es probable (2) | Catastrófica (5)   | 10        |
| RI-014 | Muy improbable (1) | Importante (4)     | 4         |
| RI-015 | Muy improbable (1) | Catastrófica (5)   | 5         |
| RI-016 | Posible (2)        | Menor (3)          | 6         |

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

| Riesgo                                                 | Estrategias de mitigación                                                                             |
| ------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| **RI-001** El LLM se equivoca al modificar un problema | - Limitar el alcance de la LLM a tareas específicas (solo redacción).<br>- Revisión manual periódica. |
| **RI-002** Dependencia incompatible                    | - Pruebas de integración antes de implementar.<br>- Plan de contingencia para reemplazo.              |
| **RI-003** Inventario inexacto                         | - Revisiones rutinarias.<br>- Sistema de colas para actualizaciones concurrentes.                     |
| **RI-004** Usuarios incómodos con dificultad           | - Filtrado por dificultad.<br>- Feedback continuo para ajustes.                                       |
| **RI-005** Sobrecarga por recursos insuficientes       | - Optimización de código y consultas.<br>- Pruebas de estrés periódicas.                              |
| **RI-006** Caída de servicio externo                   | - Respaldo audiovisual (capturas, videos) para presentaciones.                                        |
| **RI-007** Error en tags de problema                   | - Permitir reportes de usuarios.<br>- Revisiones manuales periódicas.                                 |
| **RI-008** Dinero digital inexacto                     | - Sistema de respaldo para restaurar saldos.                                                          |
| **RI-009** Bug que impida redención en tienda          | - Soporte preparado para resolver rápido.<br>- Ofrecer recompensas a usuarios afectados.              |
| **RI-010** Corrupción base de datos                    | - Respaldos regulares.<br>- Monitoreo continuo.                                                       |
| **RI-011** Problemas no se refrescan correctamente     | - Caché con invalidación automática.<br>- Reportes de usuarios para problemas obsoletos.              |
| **RI-012** Eliminación accidental en base de datos     | - Respaldos.<br>- Sistema de papelera de reciclaje.                                                   |
| **RI-013** Cierre por problemas legales                | - Equipo legal y cumplimiento normativo.<br>- Contenidos originales o con licencias.                  |
| **RI-014** Desincronización con Judge0                 | - Servicio alternativo de evaluación.<br>- Reintentos automáticos.                                    |
| **RI-015** Ataque cibernético                          | - Medidas de seguridad robustas (encriptación, 2FA).<br>- Plan de respuesta a incidentes.             |
| **RI-016** Vulnerabilidades en dependencias            | - Uso de dependencias confiables y actualizadas.<br>- Uso de lock files para versiones específicas.   |

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

**Dificultades encontradas:**

No logramos correctamente unir dentro de nuestro análisis con SonarQube el Coverage de líneas que testeamos automáticamente, por lo cual no salía dentro de nuestro análisis presente. A pesar de esto, nuestro testeo manual y automatizado, evitar duplicación de código y buenas practicas aseguran una alta calidad en nuestro código entregado.

## Referencias

CodeForces. (2024). CodeForces Problem Set. https://codeforces.com/problemset
Go. (2024). The Go Programming Language. https://golang.org/

International Organization for Standardization. (2011). Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) (ISO/IEC 25010:2011). https://www.iso.org/standard/35733.html

International Organization for Standardization. (2015). Quality management systems — Requirements (ISO 9001:2015). https://www.iso.org/standard/62085.html

International Organization for Standardization. (2017). Systems and software engineering — Software life cycle processes (ISO/IEC 12207:2017). https://www.iso.org/standard/63712.html

International Organization for Standardization. (2022). Software and systems engineering — Software testing (ISO/IEC 29119:2022). https://www.iso.org/standard/79439.html

PostgreSQL. (2024). PostgreSQL Documentation. https://www.postgresql.org/docs/

React. (2024). React Documentation. https://react.dev/

Software Engineering Institute. (2018). CMMI for Development, Version 2.0. Carnegie Mellon University. https://cmmiinstitute.com/cmmi

SonarSource. (2024). SonarQube Documentation. https://docs.sonarqube.org/
