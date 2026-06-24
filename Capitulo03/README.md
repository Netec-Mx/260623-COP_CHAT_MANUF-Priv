# Uso de Copilot para visualizar el impacto conjunto en la eficiencia y confiabilidad, eliminando los silos de información operativa.

## Metadatos

| Campo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Alta (Hard) |
| **Nivel Bloom** | Aplicar |
| **Módulo** | Capítulo 3 — Integración de Datos y Eficiencia Global |
| **Versión de la guía** | 1.0 |
| **Última revisión** | 2024 |

---

## Descripción General

Esta práctica integra los tres dominios operativos de una planta de manufactura —producción, calidad y mantenimiento— en un modelo de datos unificado dentro de Microsoft Excel, con Copilot como motor de análisis conversacional. Los participantes cargarán cuatro datasets simulados, realizarán cruzamiento de variables mediante tablas dinámicas y fórmulas sugeridas por Copilot, calcularán el OEE (Overall Equipment Effectiveness) por línea de producción e identificarán correlaciones ocultas entre eventos de mantenimiento, rechazos de calidad y pérdidas de eficiencia. La práctica culmina con la construcción de un dashboard visual integrado en Excel y la redacción asistida de un resumen ejecutivo en Word, demostrando cómo Copilot rompe los silos de información operativa que históricamente han fragmentado la toma de decisiones en planta.

---

## Objetivos de Aprendizaje

Al completar esta práctica, el participante será capaz de:

- [ ] **Integrar** datos de producción, calidad y mantenimiento en un modelo unificado en Excel utilizando Copilot para eliminar silos de información operativa.
- [ ] **Calcular** el OEE (Disponibilidad × Rendimiento × Calidad) por línea de producción con fórmulas sugeridas y validadas mediante Copilot en Excel.
- [ ] **Identificar** correlaciones entre eventos de mantenimiento correctivo, indicadores de calidad y pérdidas de eficiencia a través de análisis conversacional con Copilot.
- [ ] **Construir** un dashboard integrado de eficiencia y confiabilidad operativa con visualizaciones generadas con asistencia de Copilot en Excel.
- [ ] **Generar** un resumen ejecutivo en Word que articule los hallazgos de los tres dominios operativos utilizando Copilot como redactor asistido.

---

## Prerrequisitos

### Conocimientos Previos

| Área | Nivel requerido |
|---|---|
| Microsoft Excel (tablas, fórmulas básicas, tablas dinámicas) | Intermedio |
| Comprensión del indicador OEE y sus tres componentes (Disponibilidad, Rendimiento, Calidad) | Básico-Intermedio |
| Uso básico de Copilot en Excel y Copilot Chat | Básico (cubierto en Prácticas 1 y 2) |
| Navegación en OneDrive for Business | Básico |

### Acceso y Recursos

- [ ] Cuenta corporativa Microsoft 365 con licencia **Copilot activa** verificada.
- [ ] Acceso a **Microsoft Excel** (versión 2308 o posterior, Microsoft 365 Apps).
- [ ] Acceso a **Microsoft Word** (versión 2308 o posterior).
- [ ] Acceso a **OneDrive for Business** con al menos 5 GB de espacio disponible.
- [ ] Archivos de práctica disponibles en OneDrive:
  - `dataset_produccion.xlsx`
  - `dataset_calidad_SKU.xlsx`
  - `dataset_OT_correctivo.xlsx`
  - `dataset_refacciones.xlsx` *(referencia de Práctica 2)*
- [ ] Haber completado las **Prácticas 1 y 2**, o contar con los entregables equivalentes proporcionados por el instructor.

> **⚠️ Nota sobre privacidad:** Todos los datasets utilizados en esta práctica son simulados y anonimizados. No cargues datos reales de producción de tu empresa en Copilot Chat sin verificar que estás usando el **modo Trabajo (Work mode)** protegido en `copilot.microsoft.com` con tu cuenta corporativa.

---

## Entorno de Laboratorio

### Hardware Recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8va gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Almacenamiento libre | 5 GB | 10 GB |
| Resolución de pantalla | 1366 × 768 | 1920 × 1080 |
| Conexión a internet | 10 Mbps | 25 Mbps (red corporativa cableada) |

> **💡 Recomendación de conectividad:** Esta práctica tiene alta carga de análisis. Se recomienda realizarla en instalaciones con red corporativa cableada o WiFi de alta velocidad para minimizar la latencia en las respuestas de Copilot.

### Software Requerido

| Aplicación | Versión mínima | Verificación |
|---|---|---|
| Microsoft Excel | 365 Apps v2308+ | Archivo → Cuenta → Acerca de Excel |
| Microsoft Word | 365 Apps v2308+ | Archivo → Cuenta → Acerca de Word |
| Microsoft Copilot (Excel) | Integrado en M365 Apps | Ícono Copilot en cinta de opciones |
| Copilot Chat Web | copilot.microsoft.com | Iniciar sesión con cuenta corporativa |
| OneDrive for Business | Sincronización automática M365 | Ícono en bandeja del sistema |

### Configuración Inicial del Entorno

Antes de iniciar los pasos del laboratorio, ejecuta las siguientes verificaciones:

**1. Verificar acceso a Copilot en Excel:**
```
1. Abre Microsoft Excel.
2. Crea un libro en blanco.
3. Busca el ícono "Copilot" en la pestaña "Inicio" de la cinta de opciones.
4. Si el ícono aparece activo (no atenuado), el acceso está habilitado.
5. Si el ícono está atenuado: verifica que el archivo esté guardado en OneDrive (no localmente).
```

**2. Verificar modo Trabajo en Copilot Chat:**
```
1. Abre un navegador e ingresa a: https://copilot.microsoft.com
2. Inicia sesión con tu cuenta corporativa (usuario@empresa.com).
3. Confirma que en la parte superior aparece el indicador "Trabajo" (Work) activo.
4. El fondo del chat debe mostrar el tema corporativo, no el tema de consumidor.
```

**3. Cargar archivos a OneDrive:**
```
1. Abre el Explorador de archivos y navega a la carpeta OneDrive - [Tu Empresa].
2. Crea una carpeta nueva llamada: Practica_03_OEE_Integrado
3. Copia los cuatro archivos de dataset a esa carpeta:
   - dataset_produccion.xlsx
   - dataset_calidad_SKU.xlsx
   - dataset_OT_correctivo.xlsx
   - dataset_refacciones.xlsx
4. Espera a que el ícono de sincronización de OneDrive muestre la nube verde (✓).
```

---

## Pasos del Laboratorio

---

### Paso 1: Exploración y Comprensión de los Datasets con Copilot Chat

**Objetivo:** Familiarizarse con la estructura de los cuatro datasets antes de integrarlos, utilizando Copilot Chat para obtener un resumen rápido del contenido y las columnas clave de cada archivo.

**Instrucciones:**

1. Abre tu navegador y navega a `https://copilot.microsoft.com`. Confirma que estás en **modo Trabajo (Work)**.

2. En el panel de chat, inicia una nueva conversación haciendo clic en **"Nueva conversación"** (ícono de lápiz o botón correspondiente).

3. Escribe el siguiente prompt para contextualizar la sesión de trabajo:

   ```
   Actúa como analista de datos de manufactura industrial. Voy a trabajar con 
   cuatro datasets de una planta de producción:
   
   1. dataset_produccion.xlsx: Contiene registros diarios por línea de producción 
      con columnas: Fecha, Línea, Turno, Unidades_Planificadas, Unidades_Producidas, 
      Tiempo_Disponible_min, Tiempo_Operacion_min, Tiempo_Paro_No_Programado_min, 
      Tiempo_Paro_Programado_min, Velocidad_Nominal_upm, Velocidad_Real_upm.
   
   2. dataset_calidad_SKU.xlsx: Contiene inspecciones de calidad por SKU con columnas: 
      Fecha, Línea, Turno, SKU, Unidades_Inspeccionadas, Unidades_Rechazadas, 
      Tipo_Defecto, Turno_Defecto.
   
   3. dataset_OT_correctivo.xlsx: Contiene órdenes de trabajo correctivo con columnas: 
      ID_OT, Fecha_Apertura, Fecha_Cierre, Línea, Equipo, Tipo_Falla, 
      Duración_Paro_min, Técnico_Asignado, Costo_MO, Costo_Refaccion.
   
   4. dataset_refacciones.xlsx: Contiene consumo de refacciones con columnas: 
      ID_Refaccion, Descripcion, Línea, Equipo, Cantidad_Usada, Costo_Unitario, 
      Fecha_Uso, ID_OT_Relacionada.
   
   Con base en esta descripción, explícame: ¿qué columnas son las llaves de 
   cruzamiento natural entre estos datasets? ¿Qué precauciones debo tener al 
   integrarlos en Excel para evitar errores de relación?
   ```

4. Lee la respuesta de Copilot y toma nota de las **columnas clave de cruzamiento** identificadas (normalmente: `Fecha`, `Línea`, `Turno`).

5. Realiza un segundo prompt de profundización:

   ```
   Dado que los datasets comparten las columnas Fecha, Línea y Turno como llaves 
   de cruzamiento, ¿cuál es la mejor estrategia en Excel para consolidar estos 
   cuatro datasets en una tabla maestra de análisis OEE? Considera que algunos 
   días pueden tener registros de producción pero no tener órdenes de trabajo 
   correctivo (sin paros no programados). Dame los pasos conceptuales antes de 
   que empiece a trabajar en Excel.
   ```

6. Documenta la estrategia sugerida por Copilot en un archivo de texto o en el Bloc de notas como referencia para los pasos siguientes.

**Resultado Esperado:**
Copilot debe identificar `Fecha + Línea + Turno` como la clave compuesta de cruzamiento y recomendar el uso de `BUSCARX` o `SUMAR.SI.CONJUNTO` para consolidar datos, además de sugerir manejar los valores nulos (días sin paros correctivos) con cero en lugar de vacío para no afectar los cálculos de OEE.

**Verificación:**
- [ ] Copilot identificó al menos 2 columnas clave de cruzamiento entre datasets.
- [ ] La respuesta menciona el manejo de registros faltantes (LEFT JOIN conceptual o equivalente en Excel).
- [ ] Tienes documentada la estrategia de integración antes de abrir Excel.

---

### Paso 2: Creación del Libro Maestro de Integración en Excel

**Objetivo:** Crear el archivo de trabajo principal que consolidará los datos de los cuatro datasets en hojas separadas, preparado para el análisis con Copilot en Excel.

**Instrucciones:**

1. Abre **Microsoft Excel** y crea un nuevo libro en blanco.

2. Inmediatamente guarda el archivo en tu carpeta de OneDrive con el nombre:
   ```
   OEE_Dashboard_Integrado_[TusIniciales].xlsx
   ```
   > **Importante:** El archivo debe guardarse en OneDrive (no en disco local) para que Copilot en Excel esté disponible. Usa: **Archivo → Guardar como → OneDrive → Practica_03_OEE_Integrado**.

3. Renombra las hojas del libro para organizar el trabajo. Haz clic derecho en cada pestaña de hoja y selecciona **Cambiar nombre**:
   - Hoja 1 → `Produccion`
   - Hoja 2 → `Calidad`
   - Hoja 3 → `Mantenimiento`
   - Agrega una cuarta hoja (clic en el ícono `+`) → `OEE_Maestro`
   - Agrega una quinta hoja → `Dashboard`

4. Importa los datos del primer dataset. Haz clic en la hoja **`Produccion`** y luego:
   ```
   Pestaña Datos → Obtener datos → Desde libro de Excel
   → Navega a: OneDrive/Practica_03_OEE_Integrado/dataset_produccion.xlsx
   → Selecciona la tabla o hoja de datos
   → Clic en "Cargar"
   ```
   > Si el archivo ya está abierto, puedes copiar y pegar el rango de datos directamente en la hoja `Produccion`.

5. Repite el proceso de importación para los datasets restantes:
   - `dataset_calidad_SKU.xlsx` → hoja **`Calidad`**
   - `dataset_OT_correctivo.xlsx` → hoja **`Mantenimiento`**

6. Convierte cada rango de datos en una **Tabla de Excel** con nombre descriptivo. Selecciona cualquier celda dentro de los datos de la hoja `Produccion` y presiona `Ctrl + T`:
   - Tabla en hoja `Produccion` → nombre: `tbl_Produccion`
   - Tabla en hoja `Calidad` → nombre: `tbl_Calidad`
   - Tabla en hoja `Mantenimiento` → nombre: `tbl_Mantenimiento`

   Para nombrar cada tabla: **Pestaña Diseño de tabla → campo "Nombre de tabla"** (esquina superior izquierda de la cinta).

7. Guarda el archivo con `Ctrl + S` y espera a que OneDrive sincronice (ícono verde ✓).

**Resultado Esperado:**
El libro `OEE_Dashboard_Integrado_[TusIniciales].xlsx` debe tener 5 hojas visibles, con datos importados en las hojas `Produccion`, `Calidad` y `Mantenimiento`, cada uno convertido en tabla con nombre descriptivo. La hoja `OEE_Maestro` y `Dashboard` estarán vacías por ahora.

**Verificación:**
- [ ] El archivo está guardado en OneDrive (la barra de título muestra el ícono de nube).
- [ ] Las tres tablas tienen nombres descriptivos (`tbl_Produccion`, `tbl_Calidad`, `tbl_Mantenimiento`).
- [ ] El ícono de Copilot en la cinta de opciones (pestaña Inicio) está activo y no atenuado.
- [ ] Las 5 hojas existen con los nombres correctos.

---

### Paso 3: Construcción de la Tabla Maestra OEE con Asistencia de Copilot en Excel

**Objetivo:** Construir la tabla consolidada `OEE_Maestro` cruzando los tres datasets mediante fórmulas sugeridas por Copilot en Excel, calculando los tres componentes del OEE por línea, turno y fecha.

**Instrucciones:**

1. Haz clic en la hoja **`OEE_Maestro`** para activarla.

2. Crea los encabezados de la tabla maestra en la fila 1. Escribe cada encabezado en las celdas A1 a R1:

   ```
   A1: Fecha
   B1: Línea
   C1: Turno
   D1: Unidades_Planificadas
   E1: Unidades_Producidas
   F1: Tiempo_Disponible_min
   G1: Tiempo_Operacion_min
   H1: Tiempo_Paro_NoProg_min
   I1: Velocidad_Nominal_upm
   J1: Velocidad_Real_upm
   K1: Unidades_Rechazadas
   L1: Unidades_Inspeccionadas
   M1: Num_OT_Correctivas
   N1: Duracion_Total_Paro_OT_min
   O1: Disponibilidad
   P1: Rendimiento
   Q1: Calidad
   R1: OEE
   ```

3. Activa **Copilot en Excel** haciendo clic en el ícono **Copilot** en la pestaña **Inicio** de la cinta de opciones. Se abrirá el panel de Copilot en el lado derecho de la pantalla.

4. En el panel de Copilot, escribe el siguiente prompt para obtener ayuda con las fórmulas de cruzamiento:

   ```
   Tengo tres tablas en este libro de Excel:
   - tbl_Produccion con columnas: Fecha, Línea, Turno, Unidades_Planificadas, 
     Unidades_Producidas, Tiempo_Disponible_min, Tiempo_Operacion_min, 
     Tiempo_Paro_No_Programado_min, Velocidad_Nominal_upm, Velocidad_Real_upm
   - tbl_Calidad con columnas: Fecha, Línea, Turno, SKU, Unidades_Inspeccionadas, 
     Unidades_Rechazadas
   - tbl_Mantenimiento con columnas: ID_OT, Fecha_Apertura, Línea, Duración_Paro_min
   
   En la hoja OEE_Maestro, empezando en la fila 2, necesito:
   1. Una fórmula SUMAR.SI.CONJUNTO para la columna K (Unidades_Rechazadas) 
      que sume los rechazos de tbl_Calidad donde Fecha=A2, Línea=B2, Turno=C2
   2. Una fórmula SUMAR.SI.CONJUNTO para la columna L (Unidades_Inspeccionadas)
      con los mismos criterios
   3. Una fórmula CONTAR.SI.CONJUNTO para la columna M (Num_OT_Correctivas) 
      que cuente OTs de tbl_Mantenimiento donde Fecha_Apertura=A2 y Línea=B2
   4. Una fórmula SUMAR.SI.CONJUNTO para la columna N (Duracion_Total_Paro_OT_min)
      sumando Duración_Paro_min de tbl_Mantenimiento con los mismos criterios
   
   Dame las fórmulas exactas listas para copiar en Excel.
   ```

5. Revisa las fórmulas sugeridas por Copilot. **No las copies automáticamente sin validar.** Verifica que:
   - Los nombres de tabla coincidan exactamente con los que creaste (`tbl_Produccion`, `tbl_Calidad`, `tbl_Mantenimiento`).
   - Los nombres de columna coincidan con los encabezados reales de tus tablas.
   - La sintaxis de `SUMAR.SI.CONJUNTO` y `CONTAR.SI.CONJUNTO` sea correcta para tu versión de Excel en español.

6. Primero, copia los datos de `Fecha`, `Línea` y `Turno` desde `tbl_Produccion` a las columnas A, B, C de `OEE_Maestro` (puedes hacerlo con referencias directas o copiando y pegando como valores).

7. Copia también las columnas D a J (datos de producción: Unidades_Planificadas, Unidades_Producidas, tiempos y velocidades) desde `tbl_Produccion`.

8. Aplica las fórmulas sugeridas por Copilot en las columnas K, L, M y N de la fila 2 y luego arrástralas hacia abajo para cubrir todas las filas de datos.

9. Ahora solicita a Copilot las fórmulas para calcular los componentes del OEE. En el panel de Copilot escribe:

   ```
   En la misma hoja OEE_Maestro, necesito calcular los tres componentes del OEE:
   
   - Columna O (Disponibilidad): (Tiempo_Operacion_min) / (Tiempo_Disponible_min)
     Usa las columnas G y F respectivamente. El resultado debe estar entre 0 y 1.
   
   - Columna P (Rendimiento): (Velocidad_Real_upm / Velocidad_Nominal_upm)
     Usa las columnas J e I respectivamente. El resultado debe estar entre 0 y 1.
   
   - Columna Q (Calidad): (Unidades_Producidas - Unidades_Rechazadas) / Unidades_Producidas
     Usa las columnas E y K respectivamente. Incluye manejo de error si 
     Unidades_Producidas es cero (usa SI.ERROR para devolver 0 en ese caso).
   
   - Columna R (OEE): Disponibilidad × Rendimiento × Calidad (O2 × P2 × Q2)
   
   Dame las cuatro fórmulas para la fila 2, listas para copiar.
   ```

10. Aplica las fórmulas de OEE en las columnas O, P, Q y R. Formatea las columnas O, P, Q y R como **Porcentaje con 1 decimal** (selecciona las columnas → `Ctrl + 1` → Número → Porcentaje → 1 decimal).

11. Convierte el rango de `OEE_Maestro` en una tabla con nombre `tbl_OEE_Maestro` (`Ctrl + T` y asigna el nombre en Diseño de tabla).

12. Guarda el archivo con `Ctrl + S`.

**Resultado Esperado:**
La tabla `tbl_OEE_Maestro` debe contener todas las filas del dataset de producción con las columnas de calidad y mantenimiento cruzadas correctamente. Las columnas O, P, Q y R deben mostrar valores porcentuales entre 0% y 100%. El OEE típico para los datos simulados debe estar en el rango de 55%–85% dependiendo de la línea.

**Verificación:**
- [ ] La tabla `tbl_OEE_Maestro` existe y tiene las 18 columnas definidas.
- [ ] Las columnas K, L, M, N tienen valores numéricos (no errores `#¡VALOR!` ni `#N/A`).
- [ ] Las columnas O, P, Q, R muestran porcentajes con formato correcto.
- [ ] No hay valores negativos ni mayores a 100% en las columnas de OEE (si los hay, revisar fórmulas con Copilot).

---

### Paso 4: Análisis de Correlaciones con Copilot en Excel

**Objetivo:** Utilizar Copilot en Excel para identificar correlaciones entre eventos de mantenimiento correctivo, indicadores de calidad y pérdidas de OEE, descubriendo patrones que no serían visibles analizando los datasets por separado.

**Instrucciones:**

1. Con la hoja `OEE_Maestro` activa y el panel de Copilot abierto, escribe el siguiente prompt de análisis:

   ```
   Analiza la tabla tbl_OEE_Maestro y responde:
   1. ¿Cuál es el OEE promedio por Línea? Ordena de menor a mayor.
   2. ¿En qué línea el componente de Disponibilidad es el factor más limitante del OEE?
   3. ¿En qué línea el componente de Calidad es el factor más limitante del OEE?
   4. ¿Existe alguna relación visible entre los días con mayor Num_OT_Correctivas 
      y los días con OEE más bajo? Describe el patrón si existe.
   ```

2. Lee con atención la respuesta de Copilot. Si la respuesta es textual (sin tabla), solicita:

   ```
   Muestra los resultados del punto 1 como una tabla resumen con columnas: 
   Línea, OEE_Promedio, Disponibilidad_Promedio, Rendimiento_Promedio, 
   Calidad_Promedio. Redondea a 1 decimal.
   ```

3. Si Copilot ofrece la opción de **"Agregar a hoja"** o **"Insertar tabla"** para el resumen, acepta la sugerencia para insertar la tabla en una nueva hoja o en una celda específica de `OEE_Maestro`.

4. Realiza un segundo análisis de correlación más específico. En el panel de Copilot escribe:

   ```
   En la tabla tbl_OEE_Maestro:
   - Filtra los registros donde Num_OT_Correctivas >= 2 (días con alta actividad 
     de mantenimiento correctivo)
   - Para esos registros, ¿cuál es el OEE promedio comparado con los días donde 
     Num_OT_Correctivas = 0?
   - ¿Cuál es la diferencia en el componente de Disponibilidad entre ambos grupos?
   - ¿El componente de Calidad también se ve afectado en los días con alta actividad 
     correctiva, o permanece estable?
   
   Esto me ayudará a entender si el mantenimiento correctivo impacta solo la 
   disponibilidad o también la calidad del producto.
   ```

5. Documenta los hallazgos clave de Copilot. Abre el **Bloc de notas** o crea una celda de comentarios en la hoja `OEE_Maestro` (en una celda vacía fuera de la tabla, por ejemplo en T1) y escribe los 2-3 hallazgos más importantes identificados.

6. Realiza un tercer prompt para análisis por turno:

   ```
   Analiza la tabla tbl_OEE_Maestro agrupando por Turno (columna C):
   - ¿En qué turno es más alto el número promedio de unidades rechazadas?
   - ¿En qué turno es más baja la Disponibilidad promedio?
   - ¿Hay algún turno que tenga consistentemente un OEE inferior al 65%?
   Presenta los resultados en formato de tabla comparativa.
   ```

7. Guarda los hallazgos del análisis. Crea una nueva hoja en el libro llamada `Hallazgos_Analisis` y copia manualmente (o usa la función de insertar de Copilot) las tablas de resumen generadas en los pasos 2, 4 y 6.

**Resultado Esperado:**
Copilot debe identificar al menos una línea de producción donde el OEE es significativamente inferior al promedio, señalar el componente limitante (Disponibilidad, Rendimiento o Calidad), y mostrar evidencia de correlación entre días con alta actividad correctiva y caída en el OEE. El análisis por turno debe revelar diferencias estadísticamente notables entre turnos.

> **⚠️ Nota sobre variabilidad:** Las respuestas de Copilot son generativas y pueden variar entre sesiones. Los valores específicos dependerán de los datos simulados del dataset. Evalúa críticamente si los patrones identificados son coherentes con los datos antes de aceptarlos como válidos.

**Verificación:**
- [ ] Se obtuvieron tablas de resumen de OEE por Línea, por grupo de actividad correctiva y por Turno.
- [ ] Se identificó el factor limitante del OEE para al menos 2 líneas de producción.
- [ ] Se documentaron al menos 3 hallazgos clave en la hoja `Hallazgos_Analisis`.
- [ ] Los resultados son coherentes con los datos (no hay porcentajes imposibles ni contradicciones lógicas).

---

### Paso 5: Construcción del Dashboard Integrado en Excel

**Objetivo:** Construir un dashboard visual en la hoja `Dashboard` que consolide los indicadores clave de los tres dominios operativos (producción, calidad, mantenimiento) con visualizaciones generadas con asistencia de Copilot.

**Instrucciones:**

1. Haz clic en la hoja **`Dashboard`** para activarla.

2. En el panel de Copilot (asegúrate de que sigue abierto), escribe:

   ```
   Quiero crear un dashboard en la hoja Dashboard de este libro. 
   ¿Qué gráficas me recomiendas crear con los datos de tbl_OEE_Maestro 
   para mostrar de forma visual e integrada:
   1. El OEE por línea de producción
   2. La tendencia del OEE en el tiempo
   3. La distribución de unidades rechazadas por línea y turno
   4. La relación entre paros correctivos y pérdida de disponibilidad
   
   Para cada gráfica recomendada, indica: tipo de gráfica, datos del eje X, 
   datos del eje Y, y si necesito crear una tabla dinámica previa.
   ```

3. Basándote en las recomendaciones de Copilot, crea las siguientes **tablas dinámicas** como base para las gráficas. Ve a la hoja `OEE_Maestro`, selecciona cualquier celda de `tbl_OEE_Maestro` y ve a:
   ```
   Pestaña Insertar → Tabla dinámica → Nueva hoja
   ```
   
   Crea las siguientes tablas dinámicas (en hojas temporales o en `Dashboard`):

   **Tabla Dinámica 1 — OEE por Línea:**
   - Filas: `Línea`
   - Valores: `OEE` (Promedio), `Disponibilidad` (Promedio), `Rendimiento` (Promedio), `Calidad` (Promedio)

   **Tabla Dinámica 2 — Tendencia OEE en el tiempo:**
   - Filas: `Fecha`
   - Columnas: `Línea`
   - Valores: `OEE` (Promedio)

   **Tabla Dinámica 3 — Rechazos por Línea y Turno:**
   - Filas: `Línea`
   - Columnas: `Turno`
   - Valores: `Unidades_Rechazadas` (Suma)

4. Crea las gráficas desde cada tabla dinámica. Selecciona la Tabla Dinámica 1 y ve a:
   ```
   Pestaña Insertar → Gráfico de barras agrupadas
   ```
   Repite para las otras tablas dinámicas con los tipos de gráfica recomendados por Copilot (típicamente: barras para comparación por línea, líneas para tendencia temporal, barras apiladas para distribución de rechazos).

5. Mueve todas las gráficas a la hoja `Dashboard`. Haz clic derecho en cada gráfica → **Mover gráfico → Objeto en → Dashboard**.

6. Organiza las gráficas en el dashboard. Sugiere el siguiente diseño:
   ```
   [Fila superior]    [Gráfica 1: OEE por Línea - Barras]  |  [Gráfica 2: Tendencia OEE - Líneas]
   [Fila inferior]    [Gráfica 3: Rechazos por Turno - Barras Apiladas]  |  [KPIs Textuales]
   ```

7. Agrega **KPIs textuales** en la esquina inferior derecha del dashboard. En celdas de la hoja `Dashboard` (fuera del área de gráficas), escribe fórmulas que jalen valores clave de `tbl_OEE_Maestro`:

   ```excel
   =PROMEDIO(tbl_OEE_Maestro[OEE])         → "OEE Global Promedio"
   =MIN(tbl_OEE_Maestro[OEE])              → "OEE Mínimo Registrado"
   =SUMA(tbl_OEE_Maestro[Unidades_Rechazadas]) → "Total Unidades Rechazadas"
   =SUMA(tbl_OEE_Maestro[Num_OT_Correctivas])  → "Total OTs Correctivas"
   ```

8. Solicita a Copilot sugerencias de formato para el dashboard:

   ```
   El dashboard tiene 3 gráficas y 4 KPIs textuales. ¿Qué formato visual 
   me recomiendas para que sea legible en una presentación ejecutiva?
   Específicamente: colores para indicadores buenos/malos de OEE, 
   tamaño de fuente para KPIs, y si debo agregar algún elemento adicional 
   como slicers o filtros interactivos.
   ```

9. Aplica las recomendaciones de formato. Como mínimo:
   - Aplica formato condicional a los KPIs de OEE: **verde si OEE > 80%**, **amarillo si 65%–80%**, **rojo si < 65%**.
   - Agrega un título al dashboard en la celda A1: **"Dashboard Integrado de Eficiencia y Confiabilidad Operativa"** con fuente grande (18-20 pt) y negrita.
   - Agrega la fecha de actualización con `=HOY()` en una celda visible.

10. Agrega **Segmentadores de datos (Slicers)** para hacer el dashboard interactivo:
    ```
    Haz clic en cualquier tabla dinámica → Pestaña Análisis de tabla dinámica 
    → Insertar segmentación de datos → Selecciona: Línea, Turno
    ```
    Mueve los slicers al área del dashboard y conéctalos a todas las tablas dinámicas (clic derecho en slicer → Conexiones de informe → marca todas las tablas dinámicas).

11. Guarda el archivo con `Ctrl + S`.

**Resultado Esperado:**
La hoja `Dashboard` debe mostrar un panel visual profesional con al menos 3 gráficas interactivas, 4 KPIs con formato condicional, 2 segmentadores de datos (Línea y Turno) y un título descriptivo. Al cambiar los filtros de los slicers, todas las gráficas deben actualizarse simultáneamente.

**Verificación:**
- [ ] La hoja `Dashboard` contiene al menos 3 gráficas basadas en tablas dinámicas.
- [ ] Los 4 KPIs textuales muestran valores numéricos (no errores).
- [ ] El formato condicional aplica colores verde/amarillo/rojo a los indicadores de OEE.
- [ ] Los slicers de `Línea` y `Turno` filtran correctamente todas las gráficas al seleccionar una opción.
- [ ] El archivo guarda correctamente en OneDrive sin errores.

---

### Paso 6: Generación del Resumen Ejecutivo en Word con Copilot

**Objetivo:** Utilizar Copilot en Word para generar un resumen ejecutivo que articule los hallazgos de los tres dominios operativos (producción, calidad y mantenimiento) en un documento profesional listo para presentar a la gerencia de planta.

**Instrucciones:**

1. Abre **Microsoft Word** y crea un nuevo documento en blanco. Guárdalo inmediatamente en OneDrive con el nombre:
   ```
   Resumen_Ejecutivo_OEE_[TusIniciales].docx
   ```
   en la carpeta `Practica_03_OEE_Integrado`.

2. Activa **Copilot en Word** haciendo clic en el ícono **Copilot** en la pestaña **Inicio** de la cinta de opciones, o usando el atajo `Alt + I` para abrir el panel de Copilot.

3. En el panel de Copilot de Word, escribe el siguiente prompt para generar la estructura del documento:

   ```
   Redacta un resumen ejecutivo de 2 páginas para el Gerente de Planta sobre 
   el análisis integrado de eficiencia y confiabilidad operativa. 
   
   Contexto: Se analizaron datos de producción, calidad y mantenimiento de 
   una planta de manufactura durante el último trimestre, integrando tres 
   fuentes de datos que anteriormente operaban como silos de información.
   
   Hallazgos clave a incluir (usa estos datos ficticios de ejemplo):
   - OEE Global Promedio: 71.3%
   - Línea con menor OEE: Línea 3 con 58.2% (factor limitante: Disponibilidad 67%)
   - Línea con mayor OEE: Línea 1 con 83.5%
   - Los días con 2 o más OTs correctivas tienen un OEE promedio 18 puntos 
     porcentuales menor que los días sin paros correctivos (62% vs 80%)
   - El Turno 3 concentra el 47% de los rechazos de calidad totales
   - La Línea 3 tiene el mayor costo acumulado de mantenimiento correctivo 
     con $45,200 USD en el trimestre
   
   El documento debe incluir: Resumen Ejecutivo, Metodología de Análisis, 
   Hallazgos por Dominio (Producción / Calidad / Mantenimiento), 
   Correlaciones Identificadas, Recomendaciones Prioritarias (top 3) y 
   Próximos Pasos. Usa un tono profesional y orientado a la acción.
   ```

4. Revisa el borrador generado por Copilot. Evalúa críticamente:
   - ¿Las recomendaciones son coherentes con los hallazgos descritos?
   - ¿El tono es apropiado para una audiencia ejecutiva?
   - ¿La sección de Correlaciones Identificadas menciona explícitamente la eliminación de silos de información?

5. Realiza refinamientos con prompts de seguimiento. Escribe en el panel de Copilot:

   ```
   En la sección de Correlaciones Identificadas, agrega un párrafo que explique 
   cómo la integración de los tres dominios de datos (producción, calidad y 
   mantenimiento) reveló patrones que no eran visibles cuando cada departamento 
   analizaba sus datos de forma aislada. Menciona específicamente la correlación 
   entre el mantenimiento correctivo de la Línea 3 y el incremento de rechazos 
   en el Turno 3, y cómo este hallazgo no habría sido posible sin el cruzamiento 
   de datos.
   ```

6. Agrega una tabla de resumen de KPIs al documento. Solicita a Copilot:

   ```
   Inserta una tabla de resumen de KPIs con las siguientes columnas: 
   Indicador, Línea 1, Línea 2, Línea 3, Promedio Global. 
   Incluye las filas: OEE (%), Disponibilidad (%), Rendimiento (%), 
   Calidad (%), OTs Correctivas (cantidad), Unidades Rechazadas (cantidad).
   Usa los datos ficticios del análisis previo. Formatea la tabla con 
   encabezados en negrita y alternancia de colores en filas.
   ```

7. Aplica formato profesional al documento:
   - Asegúrate de que el título principal use el estilo **"Título"** de Word.
   - Los títulos de sección deben usar el estilo **"Título 1"**.
   - El cuerpo del texto debe usar el estilo **"Normal"** con fuente Calibri 11pt.
   - Agrega un encabezado con el nombre de la empresa (ficticio) y un pie de página con número de página y fecha.

8. Guarda el documento con `Ctrl + S` y verifica la sincronización con OneDrive.

**Resultado Esperado:**
El documento `Resumen_Ejecutivo_OEE_[TusIniciales].docx` debe tener entre 2 y 3 páginas con las seis secciones solicitadas, una tabla de KPIs formateada, al menos 3 recomendaciones accionables y un párrafo explícito sobre la eliminación de silos de información operativa como resultado del análisis integrado.

**Verificación:**
- [ ] El documento contiene las 6 secciones: Resumen Ejecutivo, Metodología, Hallazgos por Dominio, Correlaciones, Recomendaciones y Próximos Pasos.
- [ ] La tabla de KPIs está presente y formateada correctamente.
- [ ] El párrafo sobre eliminación de silos de información está incluido en la sección de Correlaciones.
- [ ] El documento está guardado en OneDrive y sincronizado.

---

## Validación y Pruebas

Al completar todos los pasos, realiza las siguientes pruebas de validación integral para confirmar que el laboratorio fue completado exitosamente:

### Prueba de Integridad de Datos

1. En la hoja `OEE_Maestro`, verifica que el número de filas de datos coincide con el número de registros del dataset de producción original (las filas de calidad y mantenimiento se agregan como columnas, no como filas nuevas).

2. Verifica que la suma de `Unidades_Rechazadas` en la columna K de `OEE_Maestro` sea igual o cercana a la suma de `Unidades_Rechazadas` en la tabla `tbl_Calidad` (puede haber diferencia si hay rechazos de turnos no presentes en producción). Usa:
   ```excel
   =SUMA(tbl_OEE_Maestro[Unidades_Rechazadas])
   =SUMA(tbl_Calidad[Unidades_Rechazadas])
   ```

3. Confirma que ninguna fila de `OEE_Maestro` tiene un OEE mayor a 100% o negativo. Usa:
   ```excel
   =CONTAR.SI(tbl_OEE_Maestro[OEE],">"&1)    → Debe ser 0
   =CONTAR.SI(tbl_OEE_Maestro[OEE],"<"&0)    → Debe ser 0
   ```

### Prueba de Interactividad del Dashboard

1. En la hoja `Dashboard`, haz clic en el slicer de **Línea** y selecciona únicamente "Línea 3".
2. Verifica que las 3 gráficas se actualicen mostrando solo datos de Línea 3.
3. Selecciona "Turno 3" en el slicer de Turno.
4. Verifica que las gráficas filtren por Línea 3 Y Turno 3 simultáneamente.
5. Haz clic en **"Borrar filtro"** en ambos slicers para restaurar la vista completa.

### Prueba de Coherencia del Resumen Ejecutivo

1. Abre `Resumen_Ejecutivo_OEE_[TusIniciales].docx`.
2. Verifica que los valores de OEE mencionados en el texto son coherentes con los de la tabla de KPIs del mismo documento.
3. Confirma que la sección de Recomendaciones tiene al menos 3 acciones concretas con responsable sugerido o área de acción.

### Lista de Verificación Final

| Entregable | Estado |
|---|---|
| `OEE_Dashboard_Integrado_[TusIniciales].xlsx` guardado en OneDrive | ☐ |
| Hoja `OEE_Maestro` con tabla completa y fórmulas OEE funcionales | ☐ |
| Hoja `Hallazgos_Analisis` con mínimo 3 hallazgos documentados | ☐ |
| Hoja `Dashboard` con 3 gráficas, 4 KPIs y 2 slicers interactivos | ☐ |
| `Resumen_Ejecutivo_OEE_[TusIniciales].docx` con 6 secciones completas | ☐ |
| Ambos archivos sincronizados en OneDrive (ícono verde ✓) | ☐ |

---

## Solución de Problemas

### Problema 1: El ícono de Copilot en Excel aparece atenuado y no responde

**Síntoma:** Al abrir el archivo `OEE_Dashboard_Integrado.xlsx` en Excel, el ícono de Copilot en la pestaña Inicio aparece en gris claro y al hacer clic no ocurre nada, o muestra el mensaje *"Copilot no está disponible para este archivo"*.

**Causa:** Copilot en Excel requiere que el archivo esté guardado en **OneDrive for Business o SharePoint Online**. Los archivos guardados localmente (en C:\\ o en el escritorio) no tienen acceso a Copilot. Adicionalmente, si la licencia de Copilot no está activa en la cuenta del usuario, el ícono también aparecerá atenuado.

**Solución:**
```
Paso 1 — Verificar ubicación del archivo:
  → Revisa la barra de título de Excel. Debe mostrar un ícono de nube ☁ 
    o la ruta debe comenzar con "OneDrive - [Empresa]".
  → Si el archivo está local: Archivo → Guardar como → OneDrive → 
    selecciona la carpeta Practica_03_OEE_Integrado → Guardar.
  → Cierra y vuelve a abrir el archivo desde OneDrive.

Paso 2 — Verificar licencia de Copilot:
  → En Excel: Archivo → Cuenta → verifica que aparezca "Microsoft 365 Copilot" 
    en la sección de suscripciones activas.
  → Si no aparece, contacta al administrador de TI para verificar la asignación 
    de licencia en el portal de Microsoft 365 Admin Center.

Paso 3 — Verificar inicio de sesión:
  → Archivo → Cuenta → verifica que el usuario conectado sea la cuenta 
    corporativa (usuario@empresa.com), no una cuenta personal de Microsoft.
  → Si es necesario, cierra sesión y vuelve a iniciar con la cuenta corporativa.
```

---

### Problema 2: Las fórmulas `SUMAR.SI.CONJUNTO` en `OEE_Maestro` devuelven cero en todas las filas aunque los datos existen en las tablas de origen

**Síntoma:** Después de aplicar las fórmulas sugeridas por Copilot para cruzar datos de calidad y mantenimiento, todas las celdas de las columnas K, L, M y N muestran `0` en lugar de los valores esperados. No hay mensajes de error, pero los datos no se están cruzando correctamente.

**Causa más común:** Incompatibilidad de tipos de datos en las columnas usadas como criterio de cruzamiento. La columna `Fecha` en `tbl_Produccion` puede estar almacenada como **texto** ("01/03/2024") mientras que en `tbl_Calidad` está almacenada como **fecha numérica** de Excel (45352). Cuando Excel compara texto con fecha, no encuentra coincidencias y devuelve 0. El mismo problema puede ocurrir con la columna `Línea` si en un dataset está como "Línea 1" y en otro como "L1" o "LINEA1".

**Solución:**
```
Paso 1 — Diagnosticar el tipo de dato en la columna Fecha:
  → En tbl_Produccion, selecciona una celda de la columna Fecha.
  → Observa el formato en la cinta: si muestra "Texto", hay un problema.
  → Haz lo mismo en tbl_Calidad.

Paso 2 — Estandarizar fechas como tipo Fecha (no texto):
  → Selecciona la columna Fecha problemática.
  → Datos → Texto en columnas → Delimitado → Siguiente → Siguiente → 
    Formato de columna: Fecha (DMY o MDY según el formato del dato) → Finalizar.
  → Verifica que las celdas ahora muestren formato de fecha numérica.

Paso 3 — Estandarizar valores de Línea:
  → Usa BUSCAR/REEMPLAZAR (Ctrl + H) en cada tabla para asegurarte de que 
    los valores de Línea sean idénticos en todas las tablas.
  → Ejemplo: reemplaza "L1" por "Línea 1" si hay inconsistencia.

Paso 4 — Pedir ayuda a Copilot para diagnosticar:
  → En el panel de Copilot en Excel escribe:
    "Las fórmulas SUMAR.SI.CONJUNTO devuelven 0. ¿Cómo puedo verificar si 
    las columnas Fecha y Línea tienen el mismo tipo de dato en tbl_Produccion 
    y tbl_Calidad? Dame una fórmula de diagnóstico."
  → Copilot sugerirá usar =TIPO(celda) o =CELDA("tipo",celda) para 
    identificar el tipo de dato en cada tabla.

Paso 5 — Solución alternativa si persiste el problema:
  → Agrega columnas auxiliares en cada tabla que conviertan la clave de 
    cruzamiento a texto plano:
    =TEXTO([@Fecha],"AAAA-MM-DD")&"|"&[@Línea]&"|"&[@Turno]
  → Usa esta columna auxiliar como criterio único de cruzamiento en 
    SUMAR.SI.CONJUNTO.
```

---

## Limpieza del Entorno

Al finalizar la práctica, realiza los siguientes pasos de limpieza para mantener el entorno ordenado y preparado para la siguiente práctica:

1. **Cerrar archivos abiertos:**
   - Guarda y cierra `OEE_Dashboard_Integrado_[TusIniciales].xlsx` con `Ctrl + S` y luego `Ctrl + W`.
   - Guarda y cierra `Resumen_Ejecutivo_OEE_[TusIniciales].docx`.

2. **Verificar sincronización en OneDrive:**
   ```
   → Haz clic en el ícono de OneDrive en la bandeja del sistema (esquina inferior derecha).
   → Confirma que todos los archivos muestran el ícono de nube verde (✓ sincronizado).
   → Si algún archivo muestra ícono de sincronización pendiente (⟳), espera a que termine.
   ```

3. **Organizar archivos en OneDrive:**
   ```
   → En la carpeta Practica_03_OEE_Integrado, verifica que existen:
     ✓ dataset_produccion.xlsx (archivo fuente, no modificar)
     ✓ dataset_calidad_SKU.xlsx (archivo fuente, no modificar)
     ✓ dataset_OT_correctivo.xlsx (archivo fuente, no modificar)
     ✓ dataset_refacciones.xlsx (archivo fuente, no modificar)
     ✓ OEE_Dashboard_Integrado_[TusIniciales].xlsx (entregable principal)
     ✓ Resumen_Ejecutivo_OEE_[TusIniciales].docx (entregable secundario)
   ```

4. **Cerrar Copilot Chat en el navegador:**
   - Cierra la pestaña de `copilot.microsoft.com` en el navegador.
   - Si iniciaste sesión en un equipo compartido, cierra también la sesión de Microsoft en el navegador.

5. **Nota para la siguiente práctica:**
   > Los archivos `OEE_Dashboard_Integrado_[TusIniciales].xlsx` y `Resumen_Ejecutivo_OEE_[TusIniciales].docx` serán utilizados como insumos en la **Práctica 4**. No los elimines ni los muevas de la carpeta `Practica_03_OEE_Integrado`. Si no completaste algún paso, solicita al instructor la versión pre-completada del entregable para no bloquear el avance en la siguiente sesión.

---

## Resumen

### Conceptos Clave Practicados

En esta práctica aplicaste de forma integral los conceptos centrales del **Capítulo 3: Integración de Datos y Eficiencia Global**:

| Concepto | Aplicación realizada |
|---|---|
| **Eliminación de silos de información** | Cruzamiento de tres datasets independientes (producción, calidad, mantenimiento) en una tabla maestra unificada |
| **OEE como indicador integrador** | Cálculo de Disponibilidad × Rendimiento × Calidad con fórmulas sugeridas por Copilot |
| **Análisis conversacional con Copilot** | Identificación de correlaciones entre eventos de mantenimiento correctivo y pérdidas de calidad/eficiencia |
| **Visualización ejecutiva** | Dashboard interactivo con gráficas, KPIs y segmentadores de datos en Excel |
| **Comunicación de hallazgos** | Resumen ejecutivo generado con Copilot en Word articulando los tres dominios operativos |

### Reflexión sobre el Valor de la Integración

Antes de esta práctica, los datos de producción, calidad y mantenimiento vivían en archivos separados, analizados por equipos distintos con perspectivas fragmentadas. Al integrarlos en un modelo unificado con Copilot como motor de análisis, fue posible descubrir patrones que ningún departamento podría haber identificado por sí solo: la correlación entre la actividad correctiva de una línea específica y el incremento de rechazos en un turno particular es el tipo de hallazgo que transforma el mantenimiento reactivo en mantenimiento predictivo.

Este es precisamente el puente entre el análisis de datos y la toma de decisiones estratégicas en manufactura que describe el Capítulo 3: no se trata de tener más datos, sino de conectarlos de forma coherente y oportuna.

### Recursos Adicionales

- [Documentación oficial de Copilot en Excel — Microsoft Learn](https://learn.microsoft.com/es-es/copilot/microsoft-365/copilot-excel)
- [Guía de OEE (Overall Equipment Effectiveness) — MESA International](https://www.mesa.org/resources)
- [Tablas dinámicas avanzadas en Excel — Microsoft Support](https://support.microsoft.com/es-es/office/crear-una-tabla-din%C3%A1mica-para-analizar-datos-de-una-hoja-de-c%C3%A1lculo-a9a84538-bfe9-40a9-a8e9-f99134456576)
- [Copilot en Word: redacción asistida — Microsoft Learn](https://learn.microsoft.com/es-es/copilot/microsoft-365/copilot-word)
- [Mejores prácticas para prompts efectivos en Copilot — Microsoft Adoption Hub](https://adoption.microsoft.com/es-es/copilot/)

---

> **📌 Nota del Instructor:** Recuerda revisar esta guía al menos 2 semanas antes de cada edición del curso para verificar que la ubicación del ícono de Copilot en la cinta de opciones de Excel y Word siga siendo precisa, ya que Microsoft actualiza continuamente la interfaz de sus aplicaciones. Los datasets simulados deben ser verificados para asegurar que generan resultados coherentes con los valores de referencia mencionados en esta guía (OEE entre 55%–85% por línea).
