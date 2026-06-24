# Transformación del enfoque correctivo al preventivo/predictivo. Identificación de patrones de fallas, análisis del comportamiento de refacciones y evaluación de riesgos de indisponibilidad por línea de producción.

---

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Aplicar — El participante ejecuta análisis reales con Copilot y construye entregables concretos a partir de datos operativos simulados |
| **Modalidad** | Individual con discusión grupal al cierre |
| **Práctica número** | 2 de 7 |

---

## 2. Descripción General

En esta práctica aplicarás Microsoft Copilot en Excel y Copilot Chat para transformar datos históricos de órdenes de trabajo correctivo y consumo de refacciones en inteligencia accionable de mantenimiento. Partiendo de dos datasets simulados de 12 meses de operación, identificarás patrones de fallas recurrentes, correlacionarás el comportamiento de consumo de refacciones con frecuencias de falla, y construirás una matriz de riesgo de indisponibilidad por línea de producción. El entregable final es una presentación en PowerPoint generada con Copilot que contiene la matriz de riesgos y los lineamientos de un plan de transición del mantenimiento correctivo al preventivo y predictivo.

Esta práctica conecta directamente con los tres pilares del Capítulo 2: la evolución del mantenimiento industrial, el rol analítico de Copilot, y la gestión del riesgo de indisponibilidad.

---

## 3. Objetivos de Aprendizaje

Al completar esta práctica, serás capaz de:

- [ ] **Aplicar** Copilot en Excel para identificar patrones recurrentes de fallas en equipos de producción a partir de históricos de mantenimiento correctivo de 12 meses
- [ ] **Analizar** el comportamiento de consumo de refacciones críticas y correlacionarlo con frecuencias de falla usando Copilot como asistente analítico conversacional
- [ ] **Construir** una matriz de evaluación de riesgos de indisponibilidad por línea de producción con soporte de Copilot para priorizar intervenciones preventivas
- [ ] **Formular** una estrategia de transición del mantenimiento correctivo al preventivo y predictivo basada en los patrones identificados con IA
- [ ] **Generar** una presentación ejecutiva en PowerPoint con Copilot que sintetice los hallazgos y el plan de acción

---

## 4. Prerrequisitos

### Conocimiento Previo

| Área | Nivel requerido |
|---|---|
| Uso básico de Microsoft Excel (tablas, filtros, fórmulas simples) | Básico |
| Interacción con Copilot en Excel (Práctica 1 completada o equivalente) | Básico |
| Conceptos de mantenimiento correctivo, preventivo y predictivo | Comprensión conceptual |
| Navegación en Microsoft 365 (OneDrive, Teams, PowerPoint) | Básico |

### Accesos y Archivos Requeridos

| Recurso | Estado requerido antes de iniciar |
|---|---|
| Cuenta corporativa Microsoft 365 con licencia Copilot activa | ✅ Verificado |
| Acceso a `copilot.microsoft.com` con cuenta corporativa (modo Trabajo) | ✅ Verificado |
| Archivo `dataset_OT_correctivo.xlsx` cargado en OneDrive | ✅ Disponible |
| Archivo `dataset_refacciones.xlsx` cargado en OneDrive | ✅ Disponible |
| Microsoft Excel versión 2308 o posterior | ✅ Verificado |
| Microsoft PowerPoint versión 2308 o posterior | ✅ Verificado |

> **⚠️ Nota de privacidad:** Todos los datasets utilizados en esta práctica son simulados y anonimizados. No cargues datos reales de producción o mantenimiento de tu empresa en Copilot Chat sin verificar que estés usando el **modo Trabajo protegido (Work mode)** en `copilot.microsoft.com` con tu cuenta corporativa.

---

## 5. Entorno de Laboratorio

### Hardware Recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8va gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Resolución de pantalla | 1366 × 768 | 1920 × 1080 |
| Conexión a internet | 10 Mbps | Red corporativa cableada |
| Almacenamiento libre | 5 GB | 10 GB |

### Software Requerido

| Aplicación | Versión mínima |
|---|---|
| Microsoft Excel | Microsoft 365 Apps v2308 o posterior |
| Microsoft PowerPoint | Microsoft 365 Apps v2308 o posterior |
| Microsoft Copilot Chat (Web) | `copilot.microsoft.com` con cuenta corporativa |
| OneDrive for Business | Sincronización automática activa |

### Configuración Inicial del Entorno

Antes de iniciar los pasos del laboratorio, ejecuta la siguiente verificación:

**Paso de configuración A — Verificar acceso a Copilot en Excel:**

1. Abre `dataset_OT_correctivo.xlsx` desde OneDrive en Microsoft Excel
2. En la cinta de opciones, verifica que aparezca el botón **Copilot** en la pestaña **Inicio** (Home)
3. Si el botón no aparece, asegúrate de que el archivo esté guardado en OneDrive (no en disco local) y que la tabla de datos tenga formato de **Tabla de Excel** (Ctrl+T)

**Paso de configuración B — Verificar modo Trabajo en Copilot Chat:**

1. Abre un navegador y navega a `https://copilot.microsoft.com`
2. Inicia sesión con tu cuenta corporativa Microsoft 365
3. Verifica que en la esquina superior aparezca tu nombre y el indicador **"Trabajo"** (Work) — esto confirma que las conversaciones están protegidas por la política de privacidad corporativa
4. Si aparece el modo **"Personal"**, cierra sesión y vuelve a iniciar con tu cuenta `@tuempresa.com`

**Paso de configuración C — Preparar estructura de carpetas:**

Crea la siguiente estructura en tu OneDrive para organizar los entregables de esta práctica:

```
OneDrive/
└── Curso_Copilot_Manufactura/
    └── Practica_02/
        ├── dataset_OT_correctivo.xlsx     ← ya debe estar aquí
        ├── dataset_refacciones.xlsx       ← ya debe estar aquí
        ├── analisis_patrones_fallas.xlsx  ← se creará en Paso 2
        └── presentacion_riesgos.pptx      ← se creará en Paso 5
```

---

## 6. Procedimiento Paso a Paso

> **📋 Estructura de la práctica:**
> | Paso | Actividad | Herramienta | Tiempo aprox. |
> |---|---|---|---|
> | 1 | Exploración inicial del dataset de OT correctivo | Excel + Copilot | 15 min |
> | 2 | Identificación de patrones de fallas con Copilot | Excel + Copilot | 20 min |
> | 3 | Análisis de comportamiento de refacciones | Excel + Copilot | 15 min |
> | 4 | Construcción de la matriz de riesgo de indisponibilidad | Excel + Copilot Chat | 20 min |
> | 5 | Generación de la presentación ejecutiva con Copilot | PowerPoint + Copilot | 15 min |
> | 6 | Reflexión y discusión grupal | Todos | 5 min |

---

### Paso 1: Exploración Inicial del Dataset de Órdenes de Trabajo Correctivo

**Objetivo del paso:** Familiarizarte con la estructura del dataset de OT correctivo e identificar las columnas clave que Copilot utilizará en el análisis posterior.

#### Instrucciones

1. Abre el archivo `dataset_OT_correctivo.xlsx` desde tu OneDrive. El archivo contiene las siguientes columnas:

   | Columna | Descripción |
   |---|---|
   | `ID_OT` | Identificador único de la orden de trabajo |
   | `Fecha_Falla` | Fecha en que ocurrió la falla (formato DD/MM/AAAA) |
   | `Linea_Produccion` | Línea donde ocurrió la falla (L1, L2, L3, L4, L5) |
   | `Equipo` | Nombre o código del equipo afectado |
   | `Tipo_Falla` | Categoría de la falla (eléctrica, mecánica, neumática, etc.) |
   | `Tiempo_Paro_Hrs` | Horas de paro no programado causadas por la falla |
   | `Costo_Reparacion_USD` | Costo total de la reparación en dólares |
   | `Tecnico_Responsable` | Nombre del técnico que atendió la OT |
   | `Descripcion_Falla` | Descripción textual de la falla reportada |

2. Verifica que los datos estén formateados como **Tabla de Excel**:
   - Haz clic en cualquier celda del dataset
   - Presiona **Ctrl+T** si aún no tiene formato de tabla
   - Asegúrate de marcar la opción "La tabla tiene encabezados"
   - Nombra la tabla como `TBL_OT_Correctivo` en el campo **Nombre de tabla** (pestaña Diseño de tabla)

3. Haz clic en el botón **Copilot** en la pestaña **Inicio** de la cinta de opciones. Se abrirá el panel de Copilot en el lado derecho de la pantalla.

4. Escribe el siguiente prompt en el panel de Copilot:

   ```
   Analiza esta tabla de órdenes de trabajo correctivo. 
   Dime cuántas filas tiene, qué rango de fechas cubre, 
   cuántas líneas de producción distintas aparecen y cuáles 
   son los 5 equipos con mayor número de fallas registradas.
   ```

5. Lee la respuesta de Copilot y verifica que la información sea consistente con lo que observas visualmente en el dataset.

6. Escribe un segundo prompt para obtener un resumen estadístico básico:

   ```
   Calcula el promedio de tiempo de paro por falla, el costo 
   promedio de reparación y el costo total acumulado de todas 
   las órdenes de trabajo en esta tabla.
   ```

7. Anota los valores clave en tu cuaderno de notas o en una celda de comentarios en la hoja `Resumen_Ejecutivo` (créala si no existe).

#### Salida Esperada

Copilot debe responder con:
- Número total de registros (aproximadamente 240–360 OTs para 12 meses de 5 líneas)
- Rango de fechas cubierto (enero a diciembre del año simulado)
- Lista de las 5 líneas de producción presentes
- Top 5 de equipos con mayor frecuencia de fallas
- Estadísticas de tiempo de paro promedio (esperado: 2–6 horas/falla) y costos

#### Verificación

- [ ] La tabla `TBL_OT_Correctivo` tiene formato de Tabla de Excel con nombre asignado
- [ ] Copilot respondió coherentemente a ambos prompts sin errores
- [ ] Identificaste al menos 3 equipos con alta frecuencia de fallas
- [ ] Anotaste los valores estadísticos clave para referencia posterior

> **💡 Nota pedagógica:** Si Copilot no puede analizar la tabla, verifica que el archivo esté guardado en OneDrive y no en disco local. Copilot en Excel requiere que el archivo esté en la nube para funcionar correctamente.

---

### Paso 2: Identificación de Patrones de Fallas con Copilot

**Objetivo del paso:** Usar Copilot para descubrir patrones temporales (estacionalidad, ciclos semanales) y patrones por tipo de falla que permitan anticipar cuándo y dónde ocurrirán las próximas fallas.

#### Instrucciones

1. Con el archivo `dataset_OT_correctivo.xlsx` abierto y el panel de Copilot activo, escribe el siguiente prompt:

   ```
   Crea una tabla dinámica o un resumen que muestre el número 
   de fallas por mes y por línea de producción. Identifica si 
   existe algún patrón estacional o meses con concentración 
   inusual de fallas.
   ```

2. Copilot generará una tabla de resumen o sugerirá fórmulas. Acepta la sugerencia haciendo clic en **Insertar en hoja** o **Aplicar** según aparezca en el panel.

3. Observa los resultados y escribe el siguiente prompt para profundizar en patrones por tipo de falla:

   ```
   Analiza la columna Tipo_Falla y muéstrame qué tipos de 
   falla son más frecuentes en cada línea de producción. 
   ¿Existe algún tipo de falla que sea dominante en una 
   línea específica?
   ```

4. Con base en la respuesta de Copilot, escribe un tercer prompt orientado a patrones cíclicos:

   ```
   ¿Puedes identificar si hay equipos que fallan de manera 
   recurrente con intervalos regulares (por ejemplo, cada 
   30, 45 o 60 días)? Lista los equipos que muestren este 
   comportamiento cíclico.
   ```

5. Ahora genera una visualización. Escribe el siguiente prompt:

   ```
   Crea un gráfico de barras que muestre las fallas totales 
   por mes para todas las líneas de producción combinadas. 
   Usa colores distintos para cada línea de producción.
   ```

6. Acepta el gráfico generado por Copilot. Si es necesario, ajusta el título manualmente a: **"Distribución Mensual de Fallas por Línea de Producción — 12 Meses"**

7. Guarda el archivo con el nombre `analisis_patrones_fallas.xlsx` en tu carpeta `Practica_02` en OneDrive.

#### Salida Esperada

Al completar este paso deberás tener:
- Una tabla de resumen con fallas por mes × línea de producción
- Un análisis textual de Copilot identificando al menos 2 patrones relevantes (por ejemplo: "La Línea 3 concentra el 38% de las fallas eléctricas" o "El equipo Compresor-02 falla cada 45 días aproximadamente")
- Un gráfico de barras insertado en la hoja de Excel

#### Verificación

- [ ] La tabla de resumen mensual está insertada en la hoja de Excel
- [ ] Copilot identificó al menos un patrón estacional o cíclico con respaldo en datos
- [ ] El gráfico de distribución mensual está correctamente generado y titulado
- [ ] El archivo fue guardado como `analisis_patrones_fallas.xlsx` en OneDrive

> **⚠️ Variabilidad de Copilot:** Recuerda que las respuestas de Copilot son generativas y pueden variar entre sesiones. Si la respuesta no identifica patrones claros, reformula el prompt añadiendo: *"Ordena los resultados de mayor a menor frecuencia y señala las 3 combinaciones equipo-mes con más fallas."*

---

### Paso 3: Análisis del Comportamiento de Refacciones y Correlación con Fallas

**Objetivo del paso:** Analizar el dataset de consumo de refacciones, identificar las piezas de mayor rotación y correlacionar su consumo con los equipos y líneas con mayor frecuencia de fallas identificados en el paso anterior.

#### Instrucciones

1. Abre el archivo `dataset_refacciones.xlsx` desde OneDrive. Este archivo contiene las siguientes columnas:

   | Columna | Descripción |
   |---|---|
   | `ID_Movimiento` | Identificador del movimiento de almacén |
   | `Fecha_Consumo` | Fecha en que se consumió la refacción |
   | `Linea_Produccion` | Línea donde se utilizó la refacción |
   | `Equipo` | Equipo en el que se instaló la refacción |
   | `Codigo_Refaccion` | Código SAP o interno de la refacción |
   | `Descripcion_Refaccion` | Nombre descriptivo de la pieza |
   | `Cantidad_Consumida` | Número de piezas consumidas |
   | `Costo_Unitario_USD` | Costo por unidad en dólares |
   | `Tipo_Mantenimiento` | Correctivo, Preventivo o Emergencia |

2. Aplica formato de Tabla de Excel (Ctrl+T) y nombra la tabla `TBL_Refacciones`.

3. Abre el panel de Copilot y escribe:

   ```
   Analiza esta tabla de consumo de refacciones. Identifica 
   las 10 refacciones con mayor consumo total (cantidad) 
   en los últimos 12 meses y calcula el costo total de 
   cada una. ¿Cuáles representan el mayor impacto económico?
   ```

4. Una vez obtenida la respuesta, escribe el siguiente prompt para la correlación con fallas:

   ```
   Compara el consumo de refacciones por equipo con la 
   información de fallas que tenemos. ¿Los equipos con 
   mayor consumo de refacciones correctivas coinciden con 
   los equipos de mayor frecuencia de fallas? Muestra 
   los 5 equipos con mayor correlación entre consumo 
   de refacciones y número de fallas.
   ```

   > **Nota:** Para este prompt, es posible que necesites tener ambos archivos abiertos simultáneamente en Excel. Si Copilot no puede cruzar los datos directamente, pasa al sub-paso 5.

5. **Cruce manual asistido por Copilot:** Si Copilot no puede cruzar automáticamente los dos datasets, escribe el siguiente prompt:

   ```
   Crea una columna adicional en esta tabla que clasifique 
   cada refacción como "Alta rotación" si su consumo mensual 
   promedio es mayor a 5 unidades, "Media rotación" si está 
   entre 2 y 5 unidades, y "Baja rotación" si es menor a 2 
   unidades.
   ```

6. Escribe un prompt final para obtener recomendaciones de stock preventivo:

   ```
   Basándote en los patrones de consumo identificados, 
   ¿qué refacciones deberían mantenerse en stock de 
   seguridad para soportar un plan de mantenimiento 
   preventivo? Sugiere cantidades mínimas de stock 
   para las 5 refacciones más críticas.
   ```

7. Copia las recomendaciones de Copilot en una nueva hoja llamada `Recomendaciones_Stock` dentro del archivo `analisis_patrones_fallas.xlsx`.

#### Salida Esperada

- Ranking de las 10 refacciones con mayor consumo e impacto económico
- Identificación de al menos 3 equipos donde el consumo de refacciones correctivas es consistente con alta frecuencia de fallas
- Clasificación de refacciones por nivel de rotación
- Tabla de recomendaciones de stock mínimo de seguridad

#### Verificación

- [ ] La tabla `TBL_Refacciones` tiene formato de Tabla de Excel con nombre asignado
- [ ] Se identificaron las 10 refacciones de mayor impacto económico
- [ ] Existe correlación documentada entre al menos 3 equipos de alta frecuencia de fallas y alto consumo de refacciones correctivas
- [ ] Las recomendaciones de stock están copiadas en la hoja `Recomendaciones_Stock`

---

### Paso 4: Construcción de la Matriz de Riesgo de Indisponibilidad

**Objetivo del paso:** Construir una matriz de riesgo de indisponibilidad por línea de producción usando los ejes de **Frecuencia de Falla** e **Impacto en Producción**, apoyándote en Copilot Chat para la lógica de priorización.

#### Instrucciones

**Parte A — Preparación de datos en Excel**

1. En el archivo `analisis_patrones_fallas.xlsx`, crea una nueva hoja llamada `Matriz_Riesgo`.

2. Con el panel de Copilot de Excel activo, escribe:

   ```
   Usando los datos de la tabla TBL_OT_Correctivo, crea 
   un resumen por línea de producción que incluya:
   - Número total de fallas en 12 meses
   - Tiempo total de paro acumulado (horas)
   - Costo total de reparaciones (USD)
   - Promedio de horas de paro por falla
   Inserta este resumen en la hoja activa.
   ```

3. Acepta el resumen generado por Copilot. Deberías obtener una tabla con 5 filas (una por línea) y las 4 métricas solicitadas.

4. Escribe el siguiente prompt para calcular los índices de riesgo:

   ```
   En la tabla de resumen por línea de producción, agrega 
   dos columnas nuevas:
   - "Índice_Frecuencia": escala del 1 al 5, donde 5 es 
     la línea con más fallas y 1 la de menos fallas
   - "Índice_Impacto": escala del 1 al 5, donde 5 es la 
     línea con mayor tiempo total de paro y 1 la de menor
   Luego agrega una columna "Nivel_Riesgo" que multiplique 
   ambos índices (resultado entre 1 y 25).
   ```

**Parte B — Generación de la matriz visual con Copilot Chat**

5. Abre `copilot.microsoft.com` en tu navegador. Verifica que estés en **modo Trabajo**.

6. Copia los valores de la tabla de resumen (Línea, Índice_Frecuencia, Índice_Impacto, Nivel_Riesgo) y pégalos en el chat de Copilot. Luego escribe el siguiente prompt:

   ```
   Tengo los siguientes datos de riesgo de indisponibilidad 
   por línea de producción en una planta de manufactura:
   
   [PEGA AQUÍ LOS DATOS DE TU TABLA]
   
   Basándote en estos datos, genera una descripción de una 
   matriz de riesgo 5x5 donde:
   - El eje X representa la Frecuencia de Falla (1=Baja, 5=Alta)
   - El eje Y representa el Impacto en Producción (1=Bajo, 5=Alto)
   - Las zonas de riesgo son: Verde (1-5), Amarillo (6-12), 
     Rojo (13-25)
   
   Indica en qué zona de riesgo cae cada línea de producción 
   y qué tipo de estrategia de mantenimiento recomiendas 
   para cada zona:
   - Zona Verde: Mantenimiento preventivo estándar
   - Zona Amarilla: Mantenimiento preventivo intensificado
   - Zona Roja: Implementación urgente de mantenimiento predictivo
   ```

7. Lee la respuesta de Copilot y copia el análisis en una celda de comentarios en la hoja `Matriz_Riesgo` de Excel.

8. Ahora escribe un prompt de seguimiento en Copilot Chat:

   ```
   Para las líneas de producción en zona Roja de la matriz 
   de riesgo, genera un plan de acción de 90 días para 
   iniciar la transición hacia mantenimiento predictivo. 
   El plan debe incluir: actividades clave, responsables 
   sugeridos (roles, no nombres), recursos necesarios y 
   métricas de éxito. Formato: tabla estructurada.
   ```

9. Copia el plan de 90 días generado por Copilot en un documento de Word o en una hoja nueva llamada `Plan_90_Dias` en Excel.

**Parte C — Crear el gráfico de la matriz en Excel**

10. Regresa a Excel, en la hoja `Matriz_Riesgo`, selecciona los datos de Índice_Frecuencia e Índice_Impacto de las 5 líneas.

11. Escribe en el panel de Copilot de Excel:

    ```
    Crea un gráfico de dispersión (scatter plot) usando 
    Índice_Frecuencia en el eje X e Índice_Impacto en el 
    eje Y. Etiqueta cada punto con el nombre de la línea 
    de producción. Titula el gráfico "Matriz de Riesgo de 
    Indisponibilidad por Línea de Producción".
    ```

12. Ajusta el gráfico manualmente si es necesario para asegurar que los ejes vayan de 0 a 6 y que las etiquetas sean legibles.

#### Salida Esperada

- Tabla de resumen por línea con las 4 métricas operativas
- Índices de frecuencia e impacto calculados en escala 1–5
- Puntuación de Nivel_Riesgo por línea (valor entre 1 y 25)
- Análisis de Copilot Chat clasificando cada línea en zona Verde/Amarilla/Roja
- Plan de acción de 90 días para las líneas en zona Roja
- Gráfico de dispersión (scatter plot) de la matriz de riesgo

#### Verificación

- [ ] La hoja `Matriz_Riesgo` contiene la tabla de resumen con índices calculados
- [ ] Al menos una línea de producción fue clasificada en zona Roja
- [ ] El plan de 90 días tiene al menos 5 actividades con roles y métricas
- [ ] El gráfico de dispersión está insertado y correctamente titulado

> **💡 Consejo:** Si Copilot en Excel no puede calcular los índices directamente, puedes hacerlo manualmente usando la fórmula `=JERARQUIA(valor, rango, 0)` para crear la escala 1–5 y luego pedir a Copilot que interprete los resultados.

---

### Paso 5: Generación de la Presentación Ejecutiva con Copilot en PowerPoint

**Objetivo del paso:** Usar Copilot en PowerPoint para generar una presentación ejecutiva que sintetice los hallazgos del análisis y presente el plan de transición hacia mantenimiento preventivo y predictivo.

#### Instrucciones

**Parte A — Preparar el contenido fuente**

1. Antes de abrir PowerPoint, prepara un resumen de los hallazgos clave en Copilot Chat (`copilot.microsoft.com`). Escribe el siguiente prompt:

   ```
   Voy a crear una presentación ejecutiva de 8 diapositivas 
   para la dirección de planta sobre la transición del 
   mantenimiento correctivo al preventivo y predictivo. 
   Los hallazgos clave de nuestro análisis son:
   
   1. [Inserta aquí los 3 equipos con mayor frecuencia de fallas]
   2. [Inserta aquí las 2 líneas en zona roja de la matriz de riesgo]
   3. [Inserta aquí el costo total de mantenimiento correctivo del año]
   4. [Inserta aquí las 3 refacciones de mayor impacto económico]
   
   Genera un esquema (outline) de 8 diapositivas con título 
   y puntos clave para cada una. La presentación debe tener 
   un enfoque ejecutivo: datos concretos, recomendaciones 
   claras y sentido de urgencia.
   ```

2. Revisa el esquema generado por Copilot. Ajusta o complementa los puntos clave con los datos reales obtenidos en los pasos anteriores.

**Parte B — Crear la presentación en PowerPoint**

3. Abre Microsoft PowerPoint. Crea una presentación en blanco.

4. Haz clic en el botón **Copilot** en la pestaña **Inicio** (o en **Vista** → **Copilot** según tu versión).

5. En el panel de Copilot de PowerPoint, escribe el siguiente prompt (adapta con los datos reales de tu análisis):

   ```
   Crea una presentación de 8 diapositivas para la dirección 
   de planta con el siguiente contenido:
   
   1. Portada: "Transformación del Mantenimiento: Del Enfoque 
      Correctivo al Predictivo" — Planta [nombre] — [Fecha]
   
   2. Situación actual: Resumen de 12 meses de mantenimiento 
      correctivo — [X] órdenes de trabajo, $[Y] USD en 
      reparaciones, [Z] horas de paro no programado
   
   3. Equipos críticos: Top 5 equipos con mayor frecuencia 
      de fallas y su impacto en producción
   
   4. Patrones identificados: Hallazgos de estacionalidad 
      y ciclos de falla encontrados con análisis de IA
   
   5. Análisis de refacciones: Refacciones de mayor impacto 
      económico y correlación con fallas
   
   6. Matriz de riesgo: Clasificación de líneas de producción 
      por nivel de riesgo (Verde/Amarillo/Rojo)
   
   7. Plan de transición 90 días: Actividades, responsables 
      y métricas para líneas en zona Roja
   
   8. Próximos pasos y conclusiones: Inversión requerida vs. 
      ahorro proyectado, llamada a la acción
   
   Usa un diseño profesional, con íconos y elementos visuales 
   que refuercen cada mensaje. Tono ejecutivo y orientado 
   a resultados.
   ```

6. Copilot generará las diapositivas automáticamente. Revisa cada diapositiva y realiza los siguientes ajustes:
   - **Diapositiva 2:** Reemplaza los valores de marcador de posición con los datos reales de tu análisis del Paso 1
   - **Diapositiva 3:** Inserta el gráfico de barras de fallas por equipo generado en el Paso 2 (copia y pega desde Excel)
   - **Diapositiva 6:** Inserta el gráfico de dispersión de la matriz de riesgo generado en el Paso 4

7. Para la diapositiva 7 (Plan de transición), escribe en el panel de Copilot de PowerPoint:

   ```
   En la diapositiva 7, reemplaza el contenido actual con 
   una tabla de 3 columnas: "Actividad", "Responsable" y 
   "Semana de ejecución". Incluye las 5 actividades más 
   importantes del plan de 90 días que generamos 
   anteriormente.
   ```

8. Guarda la presentación como `presentacion_riesgos.pptx` en tu carpeta `Practica_02` en OneDrive.

**Parte C — Pulido final con Copilot**

9. Con la presentación completa, escribe el siguiente prompt en el panel de Copilot de PowerPoint:

   ```
   Revisa toda la presentación y sugiere mejoras en:
   1. Consistencia del mensaje ejecutivo
   2. Claridad de los puntos clave en cada diapositiva
   3. Llamadas a la acción que falten o deban reforzarse
   ```

10. Implementa al menos 2 de las sugerencias de Copilot.

#### Salida Esperada

- Presentación de 8 diapositivas con diseño profesional
- Datos reales del análisis integrados en las diapositivas 2, 3 y 6
- Gráficos de Excel insertados correctamente
- Plan de transición de 90 días en formato de tabla en la diapositiva 7
- Archivo guardado como `presentacion_riesgos.pptx` en OneDrive

#### Verificación

- [ ] La presentación tiene exactamente 8 diapositivas con contenido coherente
- [ ] Los datos reales del análisis están integrados (no son valores de ejemplo genéricos)
- [ ] Al menos 2 gráficos de Excel están insertados en la presentación
- [ ] El plan de 90 días está visible en formato de tabla en la diapositiva 7
- [ ] El archivo está guardado en OneDrive con el nombre correcto

---

### Paso 6: Reflexión Final y Discusión Grupal

**Objetivo del paso:** Consolidar el aprendizaje conectando los hallazgos del análisis con los conceptos del Capítulo 2 y reflexionar sobre la aplicabilidad en el contexto real de cada participante.

#### Instrucciones

1. Abre `copilot.microsoft.com` (modo Trabajo) y escribe el siguiente prompt de reflexión:

   ```
   He completado un análisis de mantenimiento correctivo 
   con los siguientes hallazgos:
   - [Resume en 2-3 líneas los hallazgos más importantes 
     de tu análisis]
   
   ¿Qué estrategia de mantenimiento predictivo (basada 
   en datos de IoT, análisis de vibraciones, termografía 
   u otras técnicas) sería más adecuada para los equipos 
   en zona Roja de nuestra matriz de riesgo? ¿Cómo 
   podría Microsoft Copilot apoyar la implementación 
   continua de esta estrategia?
   ```

2. Lee la respuesta de Copilot y selecciona los 3 puntos que consideres más relevantes para tu contexto de planta.

3. Anota tu respuesta a la siguiente pregunta de reflexión diagnóstica (retomando el ejercicio de la Lección 2.1):

   > *"Al inicio del capítulo respondiste cuántos paros no programados ocurrieron en tu área el último mes y si existía un registro digital de fallas. Ahora que has realizado este análisis con Copilot, ¿qué cambiaría en tu proceso actual de toma de decisiones de mantenimiento?"*

4. **Discusión grupal (5 minutos):** Comparte con el grupo uno de los siguientes puntos:
   - El patrón de fallas más sorprendente que encontraste en el análisis
   - Una limitación o sesgo que identificaste en las respuestas de Copilot
   - Una aplicación inmediata que llevarías a tu planta esta semana

#### Salida Esperada

- Respuesta de Copilot con recomendaciones de estrategia predictiva para equipos en zona Roja
- Reflexión personal documentada sobre el cambio en el proceso de toma de decisiones
- Participación activa en la discusión grupal

#### Verificación

- [ ] Se generó al menos una recomendación de estrategia predictiva específica para los equipos identificados
- [ ] La reflexión diagnóstica está documentada por escrito
- [ ] Participaste en la discusión grupal con al menos un punto concreto

---

## 7. Validación y Pruebas

Al finalizar la práctica completa, verifica que tu carpeta `Practica_02` en OneDrive contenga los siguientes entregables:

| Entregable | Archivo | Contenido mínimo esperado |
|---|---|---|
| Análisis de patrones | `analisis_patrones_fallas.xlsx` | Hojas: `TBL_OT_Correctivo`, `Resumen_Ejecutivo`, `Matriz_Riesgo`, `Plan_90_Dias`, `Recomendaciones_Stock` |
| Gráfico de distribución mensual | Dentro de `analisis_patrones_fallas.xlsx` | Gráfico de barras con fallas por mes y línea |
| Gráfico de matriz de riesgo | Dentro de `analisis_patrones_fallas.xlsx` | Scatter plot con índices de frecuencia e impacto |
| Presentación ejecutiva | `presentacion_riesgos.pptx` | 8 diapositivas con datos reales, 2 gráficos de Excel, tabla de plan 90 días |

**Prueba de validación final:** Abre `copilot.microsoft.com` y escribe el siguiente prompt de autoevaluación:

```
Actúa como un gerente de mantenimiento industrial con 
10 años de experiencia. Voy a describirte los hallazgos 
de un análisis de mantenimiento que realicé:

[Describe en 5-8 oraciones los hallazgos clave de tu 
análisis: equipos críticos, patrones de fallas, líneas 
en zona roja y el plan de transición que propones]

¿Qué tan sólida es esta estrategia de transición? 
¿Qué aspectos críticos podrían estar faltando? 
¿Qué información adicional necesitarías para validar 
estas conclusiones en una planta real?
```

Esta prueba final te ayudará a identificar brechas en tu análisis y a fortalecer el pensamiento crítico sobre las recomendaciones de Copilot.

---

## 8. Solución de Problemas

### Problema 1: Copilot en Excel no responde o muestra el error "No se puede analizar esta tabla"

**Síntoma:** Al hacer clic en el botón Copilot y escribir un prompt, el panel muestra un mensaje de error como *"No puedo analizar este archivo"* o *"Copilot no está disponible para este documento"*, o simplemente no genera ninguna respuesta.

**Causa:** El archivo no está guardado en OneDrive o SharePoint Online. Copilot en Excel **requiere** que el archivo esté en la nube (no en disco local C:\ o D:\) para poder procesar los datos. Una causa secundaria es que los datos no tienen formato de Tabla de Excel estructurada — Copilot funciona mejor con tablas formales que con rangos de celdas sin estructura.

**Solución:**
1. Verifica la barra de título de Excel — si muestra una ruta local como `C:\Users\...`, el archivo está en disco local
2. Haz clic en **Archivo** → **Guardar una copia** → selecciona **OneDrive - [Tu empresa]** como destino
3. Cierra el archivo y vuelve a abrirlo desde OneDrive (usando el explorador de archivos de OneDrive o desde `office.com`)
4. Verifica que los datos tengan formato de Tabla de Excel: haz clic en cualquier celda del dataset y presiona **Ctrl+T**
5. Intenta el prompt nuevamente — el botón Copilot debe estar activo (no grisado) una vez que el archivo esté en OneDrive

---

### Problema 2: Las respuestas de Copilot Chat contienen datos inventados o inconsistentes con el dataset

**Síntoma:** Al pegar datos del dataset en Copilot Chat y solicitar análisis, Copilot genera cifras, nombres de equipos o porcentajes que no corresponden a los datos proporcionados. Por ejemplo, menciona un equipo "Compresor-07" que no existe en el dataset, o calcula un total de fallas diferente al real.

**Causa:** Copilot Chat es un modelo de lenguaje generativo que puede "alucinar" (generar información plausible pero incorrecta) cuando los datos pegados en el chat son muy extensos, están mal formateados, o cuando el prompt no es suficientemente específico sobre la fuente de datos. Copilot Chat no tiene acceso directo al archivo de Excel — solo procesa el texto que le pegas en el chat.

**Solución:**
1. **Reduce el volumen de datos:** En lugar de pegar todas las filas del dataset, pega únicamente el resumen o los totales relevantes (5–10 filas máximo)
2. **Reformula el prompt con instrucción explícita:** Agrega al inicio del prompt: *"Usa ÚNICAMENTE los datos que te proporciono a continuación. No inventes ni estimes valores que no estén en esta tabla."*
3. **Verifica siempre los números:** Antes de aceptar cualquier cifra de Copilot Chat, contrástala manualmente con los datos en Excel usando una fórmula simple como `=CONTAR.SI()` o una tabla dinámica
4. **Usa Copilot en Excel en lugar de Copilot Chat** para análisis cuantitativos — Copilot en Excel tiene acceso directo a los datos del archivo y comete menos errores de este tipo
5. Si el problema persiste, divide el análisis en prompts más pequeños y específicos, validando cada resultado antes de continuar con el siguiente

---

## 9. Limpieza del Entorno

Al finalizar la práctica, realiza las siguientes acciones para mantener tu entorno organizado:

1. **Cierra los archivos de Excel** correctamente guardando los cambios finales:
   - `dataset_OT_correctivo.xlsx` — cierra sin modificaciones adicionales (es el dataset fuente)
   - `dataset_refacciones.xlsx` — cierra sin modificaciones adicionales
   - `analisis_patrones_fallas.xlsx` — guarda y cierra

2. **Verifica la sincronización de OneDrive:**
   - Busca el ícono de OneDrive en la barra de tareas (nube azul o blanca)
   - Verifica que no haya errores de sincronización (el ícono debe mostrar una paloma verde ✅)
   - Si hay errores, haz clic derecho en el ícono → **Ver sincronización** para resolver conflictos

3. **Limpia el historial de Copilot Chat** si lo deseas:
   - En `copilot.microsoft.com`, puedes iniciar una nueva conversación para la siguiente práctica
   - Las conversaciones en modo Trabajo están protegidas, pero es buena práctica no dejar datos sensibles en chats abiertos

4. **Comparte los entregables** con el instructor si así se indica:
   - En OneDrive, haz clic derecho en la carpeta `Practica_02`
   - Selecciona **Compartir** → ingresa el correo del instructor
   - Configura el permiso como **"Puede ver"** (no editar)

5. **No elimines** los archivos de la carpeta `Practica_02` — serán referenciados en las Prácticas 3, 4 y 5 de este curso.

---

## 10. Resumen

### Conceptos Clave Aplicados

En esta práctica aplicaste los tres pilares del Capítulo 2 de manera práctica y tangible:

| Pilar | Cómo lo aplicaste |
|---|---|
| **Evolución del mantenimiento** | Analizaste 12 meses de datos correctivos para evidenciar la necesidad de transitar hacia un enfoque preventivo y predictivo |
| **Copilot como asistente analítico** | Usaste prompts estructurados en Excel y Copilot Chat para identificar patrones, correlaciones y generar recomendaciones que habrían requerido horas de análisis manual |
| **Gestión del riesgo de indisponibilidad** | Construiste una matriz de riesgo cuantificada con ejes de frecuencia e impacto, clasificando líneas de producción en zonas de acción prioritaria |

### Habilidades Desarrolladas

- ✅ Formulación de prompts analíticos específicos para contextos de manufactura industrial
- ✅ Uso de Copilot en Excel para análisis de datos operativos sin necesidad de programación
- ✅ Correlación de múltiples fuentes de datos (OTs + refacciones) asistida por IA
- ✅ Construcción de matrices de riesgo con lógica de priorización cuantificada
- ✅ Generación de presentaciones ejecutivas con Copilot en PowerPoint

### Reflexión sobre las Limitaciones de Copilot

Es fundamental que recuerdes que Copilot es una herramienta de apoyo, no un sustituto del criterio profesional. Durante esta práctica habrás observado que:
- Las respuestas son **generativas y variables** — dos prompts idénticos pueden producir resultados ligeramente distintos
- Copilot puede **alucinar datos** si los prompts son ambiguos o los datos de entrada son incompletos
- La **validación crítica** de cada respuesta es una responsabilidad del profesional, no de la herramienta
- El valor real de Copilot está en **acelerar el análisis** y **estructurar el pensamiento**, no en reemplazar el conocimiento del dominio

### Recursos Adicionales

| Recurso | Descripción | Enlace |
|---|---|---|
| Documentación de Copilot en Excel | Guía oficial de Microsoft para usar Copilot en análisis de datos | [learn.microsoft.com/copilot-excel](https://learn.microsoft.com/es-es/microsoft-365-copilot/microsoft-365-copilot-overview) |
| ISO 55000 — Gestión de activos | Norma internacional de referencia para gestión de activos físicos | [iso.org/standard/55088](https://www.iso.org/standard/55088.html) |
| MIT Sloan — IA en mantenimiento predictivo | Artículo académico sobre el rol de la IA en mantenimiento predictivo | [sloanreview.mit.edu](https://sloanreview.mit.edu/article/the-role-of-ai-in-predictive-maintenance/) |
| McKinsey — Industry 4.0 en manufactura | Perspectiva estratégica sobre la transformación digital en operaciones | [mckinsey.com/operations](https://www.mckinsey.com/capabilities/operations/our-insights/industry-40-reimagining-manufacturing-operations-after-covid-19) |

### Conexión con la Siguiente Práctica

Los archivos `analisis_patrones_fallas.xlsx` y `presentacion_riesgos.pptx` generados en esta práctica serán el punto de partida para la **Práctica 3**, donde profundizarás en el análisis de causa raíz de las fallas identificadas usando Copilot en Word y Teams. Asegúrate de tener ambos archivos correctamente guardados y sincronizados en OneDrive antes de la siguiente sesión.

> **📌 Recordatorio para el instructor:** Proporciona las versiones pre-completadas de `analisis_patrones_fallas.xlsx` y `presentacion_riesgos.pptx` a los participantes que no hayan podido completar esta práctica, para que puedan continuar con la Práctica 3 sin bloqueos. Estas versiones deben estar disponibles en la carpeta compartida del curso en SharePoint.

---

*Fin del Lab 02-00-01 — Práctica 2: Transformación del enfoque correctivo al preventivo/predictivo*
