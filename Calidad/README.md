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
