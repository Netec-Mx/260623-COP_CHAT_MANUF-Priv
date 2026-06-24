# Práctica 5 — Análisis de Paretos de Paradas y Matrices de Riesgos con Copilot

## Metadatos

| Campo            | Detalle                                      |
|------------------|----------------------------------------------|
| **Duración**     | 90 minutos                                   |
| **Complejidad**  | Alta                                         |
| **Nivel Bloom**  | Aplicar                                      |
| **Módulo**       | Capítulo 5 — Planeación y Correlación de Procesos |
| **Práctica**     | 5 de 7                                       |

---

## Descripción General

En esta práctica aplicarás los conceptos del Capítulo 5 para transformar datos históricos de paradas no programadas en conocimiento operativo accionable. Utilizarás **Copilot en Excel** para construir Paretos multicapa (por causa, por equipo y por turno), correlacionar variables de proceso con eventos de falla, y actualizar la **matriz de riesgos** generada en la Práctica 2 con los nuevos hallazgos. La práctica culmina con la generación de un plan de planeación de mantenimiento y producción optimizado que integra todos los análisis realizados, convirtiendo el conocimiento tácito de planta en decisiones documentadas y reproducibles.

---

## Objetivos de Aprendizaje

Al finalizar esta práctica serás capaz de:

- [ ] Construir Paretos de paradas no programadas multicapa (por causa, equipo y turno) utilizando Copilot en Excel para identificar las causas raíz de mayor impacto operativo.
- [ ] Correlacionar variables de proceso (temperatura, velocidad, presión, humedad) con eventos de falla usando Copilot para descubrir relaciones causa-efecto ocultas en los datos históricos.
- [ ] Actualizar la matriz de riesgo operativo con datos reales de paradas, asistido por Copilot para categorización y ponderación de riesgos.
- [ ] Generar un plan de planeación de mantenimiento y producción optimizado en Excel, integrando los hallazgos del análisis de Pareto y correlación de variables.

---

## Prerrequisitos

### Conocimiento Previo

| Área                                  | Nivel Requerido     |
|---------------------------------------|---------------------|
| Análisis de Pareto (Regla 80/20)      | Básico-Intermedio   |
| Matrices de riesgo (Probabilidad × Impacto) | Básico         |
| Variables de proceso en manufactura (temperatura, presión, velocidad) | Básico |
| Uso de Copilot en Excel (Prácticas 1–4) | Intermedio        |
| Navegación en Microsoft 365 y OneDrive | Básico             |

### Acceso y Recursos

| Recurso                                      | Estado Requerido                                   |
|----------------------------------------------|----------------------------------------------------|
| Cuenta corporativa Microsoft 365             | Activa con licencia Copilot habilitada             |
| Microsoft Excel (versión 2308 o posterior)   | Instalado y vinculado a cuenta corporativa         |
| Copilot Chat — copilot.microsoft.com         | Accesible en modo **Trabajo (Work)**               |
| Archivo `dataset_paradas_proceso.xlsx`       | Disponible en OneDrive (carpeta `/Practica5/`)     |
| Archivo `matriz_riesgos_P2.xlsx`             | Disponible en OneDrive (carpeta `/Practica5/`)     |
| OneDrive for Business                        | Sincronizado y con acceso de lectura/escritura     |

> ⚠️ **Nota de privacidad:** Todos los datasets utilizados en esta práctica son **simulados y anonimizados**. No cargues datos reales de producción en Copilot Chat sin verificar que estés usando el modo **Trabajo** protegido con tu cuenta corporativa.

---

## Entorno de Laboratorio

### Hardware Recomendado

| Componente       | Mínimo                                    | Recomendado                          |
|------------------|-------------------------------------------|--------------------------------------|
| Procesador       | Intel Core i5 8va gen / AMD Ryzen 5       | Intel Core i7 / AMD Ryzen 7          |
| RAM              | 8 GB                                      | 16 GB                                |
| Almacenamiento   | 5 GB libres                               | 10 GB libres                         |
| Pantalla         | 1366 × 768                                | 1920 × 1080                          |
| Conexión         | 10 Mbps estable                           | Red cableada corporativa             |

### Software Requerido

| Aplicación               | Versión Mínima                        | Verificación Rápida                      |
|--------------------------|---------------------------------------|------------------------------------------|
| Microsoft Excel          | Microsoft 365 Apps 2308               | Archivo → Cuenta → Acerca de Excel       |
| Microsoft Word           | Microsoft 365 Apps 2308               | Requerido para entregable final          |
| Copilot en Excel         | Integrado en M365 Apps 2308+          | Pestaña **Inicio** → botón **Copilot**   |
| Copilot Chat (Web)       | copilot.microsoft.com                 | Iniciar sesión con cuenta corporativa    |
| OneDrive for Business    | Incluido en Microsoft 365             | Bandeja del sistema → ícono nube         |

### Configuración Inicial del Entorno

Ejecuta los siguientes pasos **antes** de iniciar las actividades del laboratorio:

**1. Verificar sincronización de OneDrive:**
```
1. Haz clic en el ícono de OneDrive (nube) en la bandeja del sistema.
2. Confirma que el estado muestra "Sincronización completada" (ícono verde).
3. Navega a la carpeta: OneDrive > Practica5
4. Verifica que existen los archivos:
   - dataset_paradas_proceso.xlsx
   - matriz_riesgos_P2.xlsx
```

**2. Verificar acceso a Copilot en Excel:**
```
1. Abre Microsoft Excel.
2. Crea un libro en blanco.
3. En la pestaña "Inicio", busca el botón "Copilot" (ícono de chispa/estrella).
4. Si el botón no aparece: Archivo → Opciones → General → 
   verifica que "Habilitar características de Copilot" esté activo.
5. Cierra el libro en blanco sin guardar.
```

**3. Verificar acceso a Copilot Chat en modo Trabajo:**
```
1. Abre un navegador web.
2. Navega a: https://copilot.microsoft.com
3. Inicia sesión con tu cuenta corporativa (@tuempresa.com).
4. Verifica que en la parte superior aparezca el indicador "Trabajo" 
   (Work) — NO "Web".
5. Si aparece "Web", haz clic en el selector y elige "Trabajo".
```

> ⚠️ **Importante:** Esta práctica tiene mayor carga de análisis. Se recomienda usar red corporativa cableada o WiFi de alta velocidad para minimizar latencia en las respuestas de Copilot.

---

## Actividades del Laboratorio

---

### Paso 1 — Exploración y Limpieza del Dataset de Paradas con Copilot

**Objetivo:** Familiarizarse con la estructura del dataset `dataset_paradas_proceso.xlsx`, identificar la calidad de los datos y preparar el archivo para el análisis de Pareto con asistencia de Copilot en Excel.

**Instrucciones:**

1. Abre el archivo `dataset_paradas_proceso.xlsx` desde **OneDrive** (no desde una copia local):
   ```
   Abre Excel → Archivo → Abrir → OneDrive - [Tu empresa] 
   → Carpeta: Practica5 → dataset_paradas_proceso.xlsx
   ```

2. Familiarízate con la estructura del dataset. Deberás encontrar las siguientes columnas:

   | Columna               | Descripción                                      |
   |-----------------------|--------------------------------------------------|
   | `ID_Parada`           | Identificador único del evento de parada         |
   | `Fecha`               | Fecha del evento (formato DD/MM/AAAA)            |
   | `Turno`               | Turno en que ocurrió (Matutino/Vespertino/Nocturno) |
   | `Linea_Produccion`    | Línea afectada (L1 a L6)                         |
   | `Equipo`              | Equipo específico (ej. Compresor-A, Banda-3)     |
   | `Causa_Principal`     | Causa raíz categorizada                          |
   | `Duracion_Min`        | Duración de la parada en minutos                 |
   | `Temperatura_C`       | Temperatura de proceso al momento de la falla    |
   | `Velocidad_RPM`       | Velocidad del equipo al momento de la falla      |
   | `Presion_Bar`         | Presión de proceso al momento de la falla        |
   | `Humedad_Pct`         | Humedad relativa al momento de la falla          |
   | `Impacto_Unidades`    | Unidades de producción perdidas                  |

3. Convierte el rango de datos en una **Tabla de Excel** con nombre estructurado:
   ```
   a. Haz clic en cualquier celda dentro del rango de datos.
   b. Presiona Ctrl + T (o Insertar → Tabla).
   c. Verifica que "La tabla tiene encabezados" esté marcado → Aceptar.
   d. En la pestaña "Diseño de tabla", cambia el nombre a: TablaParadas
   ```

4. Abre el **panel de Copilot** en Excel haciendo clic en el botón **Copilot** en la pestaña Inicio.

5. Escribe el siguiente prompt en el panel de Copilot:

   ```
   Analiza la tabla TablaParadas y proporciona un resumen de:
   1. Total de registros en el dataset
   2. Rango de fechas cubierto
   3. Número de líneas de producción únicas
   4. Número de equipos únicos
   5. Causas principales únicas identificadas
   6. ¿Existen valores vacíos o inconsistencias en alguna columna?
   7. Duración promedio de paradas en minutos
   8. Total de unidades perdidas por impacto
   ```

6. Revisa la respuesta de Copilot. Si identifica valores vacíos o inconsistencias, escribe este prompt de seguimiento:

   ```
   Identifica todas las filas donde la columna Causa_Principal 
   esté vacía o contenga valores como "N/A", "Sin dato" o similares. 
   Muéstralas en una lista con su ID_Parada correspondiente.
   ```

7. **Guarda el archivo** con el nombre `dataset_paradas_proceso_P5.xlsx` en la carpeta `Practica5` de OneDrive:
   ```
   Archivo → Guardar una copia → OneDrive - [Tu empresa] 
   → Carpeta: Practica5 → Nombre: dataset_paradas_proceso_P5.xlsx
   ```

**Resultado Esperado:**

Copilot deberá proporcionar un resumen estructurado con estadísticas descriptivas del dataset. El dataset simulado contiene aproximadamente 250–350 registros de paradas distribuidos en 6 líneas de producción, 12–15 equipos, 8–10 causas principales y 3 turnos, cubriendo un período de 6 meses. La identificación de inconsistencias es parte del ejercicio; es normal encontrar 5–10 registros con datos faltantes.

**Verificación:**

- [ ] La tabla `TablaParadas` aparece con formato de tabla estructurada en Excel.
- [ ] Copilot generó un resumen con al menos 6 de los 8 puntos solicitados.
- [ ] El archivo `dataset_paradas_proceso_P5.xlsx` está guardado en OneDrive.
- [ ] Identificaste si existen o no valores faltantes en el dataset.

---

### Paso 2 — Construcción del Pareto de Paradas por Causa Principal

**Objetivo:** Construir el primer nivel del análisis de Pareto (por causa principal) utilizando Copilot en Excel para identificar las causas raíz que concentran el 80% del tiempo total de paradas.

**Instrucciones:**

1. En el mismo archivo `dataset_paradas_proceso_P5.xlsx`, crea una nueva hoja de cálculo y nómbrala `Pareto_Causa`:
   ```
   Clic derecho en la pestaña de hoja → Insertar → Hoja de cálculo
   → Renombrar como: Pareto_Causa
   ```

2. Regresa a la hoja con la tabla `TablaParadas` y abre el panel de Copilot. Escribe el siguiente prompt:

   ```
   Usando los datos de TablaParadas, crea una tabla resumen en la hoja 
   "Pareto_Causa" con las siguientes columnas:
   - Causa_Principal
   - Frecuencia (número de ocurrencias)
   - Duracion_Total_Min (suma de Duracion_Min por causa)
   - Porcentaje_Frecuencia (% del total de ocurrencias)
   - Porcentaje_Duracion (% del total de duración)
   - Porcentaje_Acumulado_Duracion (% acumulado ordenado de mayor a menor)
   
   Ordena los resultados de mayor a menor duración total.
   ```

3. Navega a la hoja `Pareto_Causa` para verificar que Copilot insertó la tabla resumen. Si la tabla no fue insertada automáticamente, copia los datos de la respuesta de Copilot manualmente en la hoja.

4. Con la tabla resumen ya en la hoja `Pareto_Causa`, selecciona el rango completo de datos y vuelve al panel de Copilot. Escribe:

   ```
   Con los datos de la tabla en esta hoja, crea un gráfico de Pareto 
   (barras de frecuencia ordenadas de mayor a menor + línea de 
   porcentaje acumulado con eje secundario). 
   Titúlalo: "Pareto de Paradas No Programadas por Causa Principal"
   Agrega etiquetas de datos en las barras y en la línea acumulada.
   Marca visualmente el punto donde el porcentaje acumulado cruza el 80%.
   ```

5. Ajusta el gráfico generado para que sea claramente legible:
   ```
   a. Redimensiona el gráfico para que ocupe el rango E2:N20 
      (aproximadamente).
   b. Verifica que el eje secundario (derecho) muestre valores de 0% a 100%.
   c. Verifica que las barras estén ordenadas de mayor a menor duración.
   ```

6. Regresa al panel de Copilot y solicita la interpretación analítica:

   ```
   Basándote en el Pareto de causas de paradas, responde:
   1. ¿Cuáles son las 3 causas principales que concentran el mayor 
      porcentaje acumulado de tiempo de paradas?
   2. ¿Qué porcentaje del tiempo total de paradas representan estas 3 causas?
   3. ¿Cuál es la causa con mayor frecuencia de ocurrencia vs. 
      la de mayor duración? ¿Son la misma?
   4. ¿Qué implicación operativa tiene esta diferencia para la 
      priorización de acciones de mantenimiento?
   ```

7. Copia la interpretación de Copilot en la celda `A25` de la hoja `Pareto_Causa` como texto de referencia para el reporte final.

**Resultado Esperado:**

La hoja `Pareto_Causa` deberá contener una tabla resumen ordenada con 8–10 causas y un gráfico de Pareto con barras y línea acumulada. El análisis típico del dataset simulado revelará que **3 causas** (como falla mecánica, problema eléctrico y falta de material) concentran entre el 70–85% del tiempo total de paradas. La diferencia entre la causa más frecuente y la de mayor duración es un hallazgo clave para la priorización.

**Verificación:**

- [ ] La hoja `Pareto_Causa` contiene la tabla resumen con las 6 columnas solicitadas.
- [ ] El gráfico de Pareto es visible con barras ordenadas y línea acumulada.
- [ ] El eje secundario muestra porcentajes de 0% a 100%.
- [ ] La interpretación de Copilot está copiada en la celda `A25`.
- [ ] Identificaste las 3 causas que concentran el 80% del tiempo de paradas.

---

### Paso 3 — Paretos Secundarios: Por Equipo y Por Turno

**Objetivo:** Construir los Paretos de segundo y tercer nivel (por equipo y por turno) para identificar dónde y cuándo se concentran las paradas, completando el análisis multicapa.

**Instrucciones:**

1. Crea dos nuevas hojas de cálculo: `Pareto_Equipo` y `Pareto_Turno`.

2. En el panel de Copilot (desde la hoja `TablaParadas`), escribe el siguiente prompt para el Pareto por equipo:

   ```
   Usando TablaParadas, crea una tabla resumen en la hoja "Pareto_Equipo" con:
   - Equipo
   - Frecuencia de paradas
   - Duracion_Total_Min
   - Impacto_Total_Unidades (suma de Impacto_Unidades)
   - Porcentaje_Duracion
   - Porcentaje_Acumulado_Duracion
   
   Ordena de mayor a menor duración total.
   Luego crea un gráfico de Pareto en esa hoja titulado:
   "Pareto de Paradas por Equipo — Duración e Impacto"
   ```

3. Para el Pareto por turno, escribe en Copilot:

   ```
   Usando TablaParadas, crea en la hoja "Pareto_Turno" una tabla 
   resumen con:
   - Turno (Matutino, Vespertino, Nocturno)
   - Frecuencia de paradas
   - Duracion_Total_Min
   - Duracion_Promedio_Min
   - Impacto_Total_Unidades
   - Porcentaje_del_Total_de_Paradas
   
   Incluye también un desglose por Turno × Causa_Principal 
   (tabla cruzada) para identificar qué causas dominan en cada turno.
   Crea un gráfico de barras agrupadas por turno en la misma hoja.
   ```

4. Una vez generadas ambas hojas, vuelve al panel de Copilot y solicita un análisis cruzado:

   ```
   Comparando los tres Paretos generados (por Causa, por Equipo 
   y por Turno), identifica:
   1. ¿Qué equipo tiene la mayor duración total de paradas?
   2. ¿En qué turno ocurren más paradas? ¿Y cuál tiene mayor 
      duración promedio por evento?
   3. ¿Existe alguna combinación Equipo-Causa-Turno que aparezca 
      como punto crítico en los tres análisis simultáneamente?
   4. Si tuvieras que priorizar UNA acción de mantenimiento preventivo 
      basándote en estos tres Paretos, ¿cuál sería y por qué?
   ```

5. Documenta los hallazgos del análisis cruzado en una nueva hoja llamada `Hallazgos_Pareto`:
   ```
   Crea una nueva hoja llamada "Hallazgos_Pareto".
   En la celda A1 escribe: "HALLAZGOS CLAVE — ANÁLISIS DE PARETO MULTICAPA"
   Copia la respuesta del análisis cruzado de Copilot a partir de A3.
   ```

**Resultado Esperado:**

Al completar este paso tendrás tres Paretos independientes más una hoja de hallazgos consolidados. El análisis cruzado típicamente revelará que **1–2 equipos específicos** (como una prensa o un compresor) concentran el mayor impacto, que el **turno nocturno** suele tener menor frecuencia pero mayor duración promedio por evento (por menor personal de respuesta), y que existe al menos una combinación Equipo-Causa-Turno que es recurrente como punto crítico.

**Verificación:**

- [ ] Las hojas `Pareto_Equipo` y `Pareto_Turno` existen con tablas resumen y gráficos.
- [ ] La tabla cruzada Turno × Causa está presente en `Pareto_Turno`.
- [ ] La hoja `Hallazgos_Pareto` contiene el análisis cruzado de los tres Paretos.
- [ ] Identificaste la combinación Equipo-Causa-Turno más crítica.
- [ ] Guardaste el archivo (Ctrl + S).

---

### Paso 4 — Análisis de Correlación entre Variables de Proceso y Eventos de Falla

**Objetivo:** Aplicar el concepto central de la Lección 5.2 — correlación de variables de proceso y fallas con IA — para descubrir relaciones estadísticas entre parámetros operativos (temperatura, velocidad, presión, humedad) y la ocurrencia/duración de paradas.

**Instrucciones:**

1. Crea una nueva hoja llamada `Correlacion_Variables`.

2. En el panel de Copilot (desde la hoja `TablaParadas`), escribe:

   ```
   Analiza la correlación entre las variables de proceso y los 
   eventos de falla en TablaParadas. Específicamente:
   
   1. Calcula el coeficiente de correlación de Pearson entre 
      Duracion_Min y cada una de estas variables:
      - Temperatura_C
      - Velocidad_RPM
      - Presion_Bar
      - Humedad_Pct
   
   2. Presenta los resultados en una tabla con columnas:
      Variable | Correlación con Duracion_Min | Interpretación 
      (positiva fuerte/débil/negativa fuerte/débil/sin correlación)
   
   3. ¿Qué variable muestra la correlación más fuerte con la 
      duración de las paradas?
   
   Coloca la tabla en la hoja "Correlacion_Variables".
   ```

3. Una vez obtenida la tabla de correlaciones, profundiza con este prompt:

   ```
   Para la variable con mayor correlación con Duracion_Min, 
   realiza el siguiente análisis adicional:
   
   1. Divide los registros en tres rangos de valor de esa variable 
      (bajo, medio, alto) usando percentiles 33 y 67 como puntos de corte.
   2. Calcula la duración promedio de paradas para cada rango.
   3. ¿Existe un umbral crítico donde la duración de paradas 
      aumenta significativamente?
   4. ¿Este umbral varía según la Causa_Principal o el Equipo?
   
   Presenta los resultados en tablas y agrega una interpretación 
   operativa en lenguaje de planta.
   ```

4. Solicita a Copilot la creación de un gráfico de dispersión para visualizar la correlación más significativa:

   ```
   Crea un gráfico de dispersión (scatter plot) en la hoja 
   "Correlacion_Variables" que muestre:
   - Eje X: [variable con mayor correlación]
   - Eje Y: Duracion_Min
   - Cada punto representa un evento de parada
   - Agrega una línea de tendencia lineal con ecuación y R²
   - Colorea los puntos según Causa_Principal si es posible
   
   Titúlalo: "Correlación entre [Variable] y Duración de Paradas"
   ```

5. Usa **Copilot Chat** (copilot.microsoft.com en modo Trabajo) para una interpretación más profunda. Copia y pega los datos de la tabla de correlaciones en Copilot Chat y escribe:

   ```
   Soy supervisor de producción en una planta de manufactura. 
   Analicé la correlación entre variables de proceso y la duración 
   de paradas no programadas. Los resultados son:
   
   [PEGA AQUÍ LA TABLA DE CORRELACIONES]
   
   Basándote en estos resultados:
   1. ¿Qué acciones de mantenimiento preventivo específicas 
      recomendarías para las 2 variables con mayor correlación?
   2. ¿Cómo diferenciarías entre correlación y causalidad en 
      este contexto? ¿Qué análisis adicional sería necesario?
   3. ¿Cómo incorporarías estos umbrales críticos en un sistema 
      de alertas tempranas de mantenimiento?
   4. Redacta un párrafo ejecutivo (máximo 100 palabras) que 
      explique este hallazgo a la dirección de planta.
   ```

6. Guarda la respuesta de Copilot Chat en la hoja `Correlacion_Variables`, celda `A30`.

**Resultado Esperado:**

La tabla de correlaciones mostrará que al menos 2 variables tienen correlación moderada-alta (|r| > 0.4) con la duración de paradas. En el dataset simulado, típicamente **Temperatura_C** y **Presion_Bar** muestran las correlaciones más fuertes. El análisis de umbrales revelará un punto de inflexión (por ejemplo, temperatura > 85°C correlaciona con paradas 40% más largas). El gráfico de dispersión con línea de tendencia y R² será el artefacto visual clave para comunicar este hallazgo.

**Verificación:**

- [ ] La hoja `Correlacion_Variables` contiene la tabla de correlaciones de Pearson con las 4 variables.
- [ ] El análisis de rangos (bajo/medio/alto) identifica un umbral crítico.
- [ ] El gráfico de dispersión con línea de tendencia y R² está creado.
- [ ] La interpretación ejecutiva de Copilot Chat está guardada en la celda `A30`.
- [ ] Comprendes la diferencia entre correlación y causalidad en este contexto.

---

### Paso 5 — Actualización de la Matriz de Riesgos con Hallazgos del Análisis

**Objetivo:** Integrar los hallazgos del análisis de Pareto y correlación de variables para actualizar la matriz de riesgos operativos de la Práctica 2, incorporando nuevas categorías de riesgo y ponderaciones basadas en datos reales.

**Instrucciones:**

1. Abre el archivo `matriz_riesgos_P2.xlsx` desde OneDrive en una **nueva ventana de Excel** (para mantener ambos archivos abiertos simultáneamente):
   ```
   Excel → Archivo → Abrir → OneDrive → Practica5 → matriz_riesgos_P2.xlsx
   ```

2. Familiarízate con la estructura de la matriz de riesgos existente. Deberás encontrar:
   - Riesgos identificados previamente (columna `Riesgo`)
   - Probabilidad de ocurrencia (escala 1–5)
   - Impacto operativo (escala 1–5)
   - Nivel de riesgo = Probabilidad × Impacto
   - Acciones de mitigación existentes

3. Guarda una copia de trabajo con nuevo nombre:
   ```
   Archivo → Guardar una copia → OneDrive → Practica5 
   → Nombre: matriz_riesgos_P5_actualizada.xlsx
   ```

4. En el panel de Copilot del archivo de la matriz, escribe:

   ```
   Tengo una matriz de riesgos operativos de planta. Necesito 
   actualizarla con nuevos hallazgos del análisis de paradas.
   
   Los nuevos hallazgos son:
   - Las 3 causas principales de paradas concentran el 80% 
     del tiempo de paradas (identifiqué: [ESCRIBE LAS 3 CAUSAS 
     QUE ENCONTRASTE EN EL PASO 2])
   - El equipo más crítico es [ESCRIBE EL EQUIPO DEL PASO 3] 
     con [X] minutos de paradas totales
   - El turno con mayor duración promedio es [TURNO DEL PASO 3]
   - La variable de proceso con mayor correlación con duración 
     de paradas es [VARIABLE DEL PASO 4] con r=[VALOR]
   - El umbral crítico identificado es: [UMBRAL DEL PASO 4]
   
   Basándote en estos datos, sugiere:
   1. Qué riesgos existentes en la matriz deben aumentar su 
      calificación de probabilidad o impacto
   2. Qué riesgos nuevos deben agregarse que no estaban 
      contemplados originalmente
   3. Qué acciones de mitigación específicas deben actualizarse
   ```

   > 📝 **Nota:** Reemplaza los valores entre corchetes `[ ]` con los hallazgos reales que obtuviste en los pasos anteriores.

5. Implementa las actualizaciones sugeridas por Copilot en la matriz:
   ```
   a. Para riesgos existentes a actualizar:
      - Cambia los valores de Probabilidad y/o Impacto según 
        la recomendación de Copilot
      - Agrega una columna "Fecha_Actualización" con la fecha actual
      - Agrega una columna "Fuente_Actualización" con valor: 
        "Análisis Pareto P5 - [Fecha]"
   
   b. Para riesgos nuevos a agregar:
      - Inserta nuevas filas al final de la tabla de riesgos
      - Completa todas las columnas: Riesgo, Probabilidad, 
        Impacto, Nivel_Riesgo, Acción_Mitigación, 
        Fecha_Actualización, Fuente_Actualización
   ```

6. Solicita a Copilot que actualice el mapa visual de la matriz de riesgos:

   ```
   Con la matriz actualizada, crea un mapa de calor de riesgos 
   (heat map) en una nueva hoja llamada "Mapa_Riesgos_P5" donde:
   - Eje X: Probabilidad (1 a 5)
   - Eje Y: Impacto (1 a 5)
   - Cada celda de la grilla muestre los riesgos ubicados en 
     esa combinación Probabilidad × Impacto
   - Usa colores: Verde (riesgo bajo 1-4), Amarillo (medio 5-9), 
     Naranja (alto 10-14), Rojo (crítico 15-25)
   - Destaca con borde grueso los riesgos que fueron 
     actualizados o agregados en esta práctica
   ```

7. Guarda el archivo (Ctrl + S).

**Resultado Esperado:**

La matriz actualizada deberá contener al menos 3–5 riesgos con calificaciones modificadas y 2–4 riesgos nuevos derivados directamente de los hallazgos del análisis de Pareto y correlación. El mapa de calor visualizará la distribución de riesgos antes y después de la actualización, mostrando que varios riesgos se movieron hacia zonas de mayor criticidad al incorporar datos reales de paradas.

**Verificación:**

- [ ] El archivo `matriz_riesgos_P5_actualizada.xlsx` está guardado en OneDrive.
- [ ] Al menos 3 riesgos existentes fueron actualizados con nueva calificación.
- [ ] Al menos 2 riesgos nuevos fueron agregados con fuente de datos documentada.
- [ ] Las columnas `Fecha_Actualización` y `Fuente_Actualización` están presentes.
- [ ] El mapa de calor en la hoja `Mapa_Riesgos_P5` está creado con código de colores.

---

### Paso 6 — Generación del Plan de Planeación Optimizado con Copilot

**Objetivo:** Aplicar los hallazgos del análisis de Pareto, correlación de variables y matriz de riesgos para generar un plan de planeación de mantenimiento y producción optimizado en Excel, integrando todos los insights obtenidos en esta práctica.

**Instrucciones:**

1. En el archivo `dataset_paradas_proceso_P5.xlsx`, crea una nueva hoja llamada `Plan_Planeacion_Optimizado`.

2. En el panel de Copilot, escribe el siguiente prompt de generación del plan:

   ```
   Soy el jefe de planeación de una planta de manufactura. 
   Basándome en el análisis de paradas de los últimos 6 meses, 
   necesito generar un plan de planeación de mantenimiento 
   preventivo para las próximas 12 semanas.
   
   Mis hallazgos clave son:
   - Causas críticas (80% del tiempo de paradas): 
     [CAUSAS DEL PASO 2]
   - Equipos más críticos: [EQUIPOS DEL PASO 3]
   - Turno con mayor vulnerabilidad: [TURNO DEL PASO 3]
   - Variable de proceso crítica: [VARIABLE DEL PASO 4] 
     con umbral de alerta en [UMBRAL DEL PASO 4]
   - Riesgos actualizados de mayor criticidad: 
     [TOP 3 RIESGOS DEL PASO 5]
   
   Crea en la hoja "Plan_Planeacion_Optimizado" una tabla 
   de planeación con las columnas:
   - Semana (1 a 12)
   - Equipo_Prioritario
   - Actividad_Mantenimiento
   - Tipo (Preventivo/Predictivo/Correctivo_Planificado)
   - Duración_Estimada_Horas
   - Turno_Recomendado (considerando el turno más crítico)
   - Responsable_Área
   - Indicador_Control (variable a monitorear)
   - Umbral_Alerta
   - Prioridad (Alta/Media/Baja)
   
   Prioriza las semanas 1-4 con acciones en los equipos 
   y causas más críticos identificados.
   ```

3. Revisa el plan generado y solicita ajustes de escenario aplicando el concepto de la Lección 5.3:

   ```
   Ahora simula el siguiente escenario de optimización:
   
   Escenario: La planta tiene disponibilidad limitada de 
   técnicos de mantenimiento — máximo 2 actividades de 
   mantenimiento preventivo por semana sin afectar la 
   producción.
   
   Con esta restricción:
   1. ¿Qué actividades del plan deben reprogramarse o 
      combinarse para cumplir la restricción?
   2. ¿Cuál es el riesgo operativo de posponer las 
      actividades de menor prioridad?
   3. Genera una versión "Plan Restringido" del cronograma 
      que respete el límite de 2 actividades por semana, 
      priorizando las de mayor impacto en reducción de 
      tiempo de paradas.
   
   Agrega el Plan Restringido en una segunda tabla en la 
   misma hoja, debajo del plan original.
   ```

4. Agrega indicadores de seguimiento al plan:

   ```
   Al final de la hoja "Plan_Planeacion_Optimizado", 
   crea una sección de KPIs de seguimiento del plan con:
   
   - Total de horas de mantenimiento planificadas (semanas 1-12)
   - Reducción esperada de tiempo de paradas (%) si se 
     ejecuta el 100% del plan
   - Reducción esperada si se ejecuta el Plan Restringido
   - Equipos cubiertos vs. total de equipos críticos
   - Indicadores de alerta temprana a monitorear 
     (basados en las variables de proceso correlacionadas)
   
   Usa fórmulas de Excel donde sea posible para que los 
   KPIs se calculen automáticamente.
   ```

5. Aplica formato profesional al plan:
   ```
   a. Selecciona la tabla del plan completo.
   b. Aplica formato condicional:
      - Prioridad Alta → fondo rojo claro
      - Prioridad Media → fondo amarillo claro
      - Prioridad Baja → fondo verde claro
   c. Congela la primera fila (Vista → Inmovilizar → 
      Inmovilizar fila superior).
   d. Aplica filtros automáticos a la tabla.
   ```

6. Guarda el archivo final (Ctrl + S).

**Resultado Esperado:**

La hoja `Plan_Planeacion_Optimizado` deberá contener un plan de 12 semanas con 15–25 actividades de mantenimiento preventivo/predictivo, una versión restringida del plan con máximo 2 actividades semanales, y una sección de KPIs con fórmulas activas. El plan deberá mostrar claramente cómo los hallazgos del análisis de Pareto y correlación se traducen en acciones concretas de mantenimiento.

**Verificación:**

- [ ] La hoja `Plan_Planeacion_Optimizado` contiene el plan completo de 12 semanas con las 10 columnas solicitadas.
- [ ] El Plan Restringido (máximo 2 actividades/semana) está presente debajo del plan original.
- [ ] La sección de KPIs con fórmulas de Excel está creada.
- [ ] El formato condicional por prioridad (rojo/amarillo/verde) está aplicado.
- [ ] Los filtros automáticos están activos en la tabla.

---

### Paso 7 — Consolidación de Entregables y Generación de Resumen Ejecutivo

**Objetivo:** Consolidar todos los entregables de la práctica y generar un resumen ejecutivo en Word asistido por Copilot que integre los hallazgos del análisis de Pareto, correlación de variables, actualización de riesgos y plan de planeación.

**Instrucciones:**

1. Abre **Microsoft Word** y crea un nuevo documento en blanco. Guárdalo inmediatamente en OneDrive:
   ```
   Archivo → Guardar como → OneDrive → Practica5 
   → Nombre: Resumen_Ejecutivo_Analisis_Paradas_P5.docx
   ```

2. Abre el panel de Copilot en Word (pestaña **Inicio** → botón **Copilot** o usa el ícono de Copilot en el lienzo).

3. Escribe el siguiente prompt en Copilot de Word para generar la estructura del resumen:

   ```
   Genera un resumen ejecutivo de análisis de paradas no programadas 
   para una planta de manufactura con la siguiente estructura:
   
   1. RESUMEN EJECUTIVO (máximo 150 palabras)
   2. HALLAZGOS PRINCIPALES DEL ANÁLISIS DE PARETO
      - Pareto por Causa Principal
      - Pareto por Equipo
      - Pareto por Turno
      - Análisis cruzado multicapa
   3. CORRELACIONES DE VARIABLES DE PROCESO IDENTIFICADAS
      - Variables con mayor correlación con duración de paradas
      - Umbrales críticos identificados
      - Implicaciones operativas
   4. ACTUALIZACIÓN DE MATRIZ DE RIESGOS
      - Riesgos actualizados
      - Nuevos riesgos identificados
      - Cambios en nivel de criticidad
   5. PLAN DE PLANEACIÓN OPTIMIZADO
      - Actividades prioritarias (semanas 1-4)
      - Restricciones y escenario ajustado
      - KPIs de seguimiento
   6. RECOMENDACIONES Y PRÓXIMOS PASOS
   
   Usa un tono ejecutivo, orientado a la toma de decisiones. 
   Deja marcadores de posición [DATO] donde se deben insertar 
   los valores específicos del análisis.
   ```

4. Una vez generada la estructura, completa los marcadores de posición `[DATO]` con los hallazgos reales de tu análisis:
   ```
   Reemplaza manualmente cada [DATO] con los valores que 
   obtuviste en los pasos 2, 3, 4, 5 y 6 de esta práctica.
   ```

5. Solicita a Copilot en Word que mejore la sección de recomendaciones:

   ```
   Expande la sección "Recomendaciones y Próximos Pasos" 
   con al menos 5 recomendaciones específicas y accionables, 
   cada una con:
   - Acción concreta
   - Responsable sugerido (área/rol)
   - Plazo de implementación (corto: 0-30 días, 
     mediano: 31-90 días, largo: 91-180 días)
   - Beneficio esperado en términos de reducción de 
     tiempo de paradas o mejora de disponibilidad
   ```

6. Agrega una tabla de resumen al documento:

   ```
   Inserta al inicio del documento (después del título) 
   una tabla de resumen rápido con:
   | Indicador | Valor Actual | Meta Propuesta |
   Incluye: Total paradas analizadas, Tiempo total paradas (hrs), 
   Causas críticas identificadas, Equipos en zona roja, 
   Reducción esperada con plan completo (%), 
   Reducción con plan restringido (%)
   ```

7. Guarda el documento (Ctrl + S).

**Resultado Esperado:**

El documento `Resumen_Ejecutivo_Analisis_Paradas_P5.docx` deberá tener entre 3–5 páginas con las 6 secciones estructuradas, la tabla de resumen al inicio, y al menos 5 recomendaciones con responsable, plazo y beneficio esperado. El documento debe ser directamente utilizable para una presentación a dirección de planta.

**Verificación:**

- [ ] El documento Word está guardado en OneDrive con el nombre correcto.
- [ ] Las 6 secciones del resumen ejecutivo están presentes y completas.
- [ ] Los marcadores `[DATO]` fueron reemplazados con valores reales del análisis.
- [ ] La tabla de resumen rápido está al inicio del documento.
- [ ] Las 5 recomendaciones incluyen responsable, plazo y beneficio esperado.

---

## Validación y Pruebas

Al finalizar todos los pasos, realiza las siguientes verificaciones de calidad para confirmar que la práctica fue completada correctamente:

### Lista de Verificación de Entregables

| Entregable                                      | Ubicación en OneDrive                  | Estado |
|-------------------------------------------------|----------------------------------------|--------|
| `dataset_paradas_proceso_P5.xlsx`               | `/Practica5/`                          | ☐      |
| → Hoja: `TablaParadas` (tabla estructurada)     | Dentro del archivo Excel               | ☐      |
| → Hoja: `Pareto_Causa` (tabla + gráfico)        | Dentro del archivo Excel               | ☐      |
| → Hoja: `Pareto_Equipo` (tabla + gráfico)       | Dentro del archivo Excel               | ☐      |
| → Hoja: `Pareto_Turno` (tabla cruzada + gráfico)| Dentro del archivo Excel               | ☐      |
| → Hoja: `Hallazgos_Pareto`                      | Dentro del archivo Excel               | ☐      |
| → Hoja: `Correlacion_Variables` (tabla + scatter)| Dentro del archivo Excel              | ☐      |
| → Hoja: `Plan_Planeacion_Optimizado`            | Dentro del archivo Excel               | ☐      |
| `matriz_riesgos_P5_actualizada.xlsx`            | `/Practica5/`                          | ☐      |
| → Hoja: `Mapa_Riesgos_P5` (heat map)           | Dentro del archivo Excel               | ☐      |
| `Resumen_Ejecutivo_Analisis_Paradas_P5.docx`    | `/Practica5/`                          | ☐      |

### Pruebas de Calidad Analítica

**Prueba 1 — Consistencia del Pareto:**
```
Verifica que en la hoja Pareto_Causa:
- La columna Porcentaje_Acumulado_Duracion llega exactamente a 100%
  en la última fila.
- La suma de Porcentaje_Duracion de todas las causas = 100%.
- El gráfico muestra las barras en orden descendente (no ascendente).
```

**Prueba 2 — Validez de la Correlación:**
```
Verifica en la hoja Correlacion_Variables:
- Los coeficientes de Pearson están en el rango [-1, 1].
- El gráfico de dispersión tiene línea de tendencia con R² visible.
- La variable identificada como "más correlacionada" tiene el 
  mayor valor absoluto de r en la tabla.
```

**Prueba 3 — Integridad de la Matriz de Riesgos:**
```
Verifica en matriz_riesgos_P5_actualizada.xlsx:
- Nivel_Riesgo = Probabilidad × Impacto para TODOS los registros.
- Los riesgos nuevos tienen la columna Fuente_Actualización completada.
- El mapa de calor refleja los colores correctos según la escala 
  definida (verde/amarillo/naranja/rojo).
```

**Prueba 4 — Coherencia del Plan de Planeación:**
```
Verifica en la hoja Plan_Planeacion_Optimizado:
- El Plan Restringido no tiene más de 2 actividades en ninguna semana.
- Las actividades de Prioridad Alta están concentradas en semanas 1-4.
- Los KPIs con fórmulas devuelven valores numéricos (no errores #REF! 
  ni #VALUE!).
```

---

## Solución de Problemas

### Problema 1 — Copilot en Excel no Genera las Tablas Resumen en la Hoja Indicada

**Síntoma:** Al solicitar a Copilot que cree una tabla resumen en una hoja específica (por ejemplo, `Pareto_Causa`), Copilot genera la tabla en la hoja activa actual o muestra un mensaje de que no puede insertar en otra hoja directamente.

**Causa:** Copilot en Excel opera principalmente en la hoja activa. No tiene la capacidad de insertar contenido directamente en una hoja diferente a la que está activa en el momento del prompt. Esta es una limitación conocida de Copilot en Excel a partir de la versión 2308.

**Solución:**
```
1. Navega primero a la hoja destino (ej. clic en pestaña "Pareto_Causa").
2. Asegúrate de que la hoja destino esté activa (visible en pantalla).
3. Vuelve a escribir el prompt a Copilot, ahora sin mencionar el nombre 
   de la hoja destino: simplemente pide "crea una tabla resumen aquí 
   con las siguientes columnas..."
4. Copilot insertará la tabla en la hoja activa.
5. Alternativa: Solicita a Copilot que genere la tabla en la hoja actual 
   y luego muévela manualmente a la hoja correcta usando 
   Ctrl+X → navegar a hoja destino → Ctrl+V.
6. Si el problema persiste con el análisis de TablaParadas desde otra hoja:
   asegúrate de que TablaParadas esté nombrada correctamente 
   (Diseño de tabla → Nombre de tabla) para que Copilot pueda 
   referenciarla desde cualquier hoja.
```

---

### Problema 2 — Latencia Alta o Respuestas Incompletas de Copilot en el Análisis de Correlación (Paso 4)

**Síntoma:** Al solicitar el análisis de correlación de Pearson entre variables de proceso y duración de paradas, Copilot tarda más de 60 segundos en responder, la respuesta se corta a la mitad, o Copilot devuelve un mensaje de error indicando que no puede procesar el análisis con el dataset completo.

**Causa:** El análisis de correlación sobre datasets con 250–350 registros y múltiples variables simultáneas es una de las operaciones de mayor carga computacional para Copilot en Excel. La latencia se agrava cuando la conexión a internet es inestable (< 10 Mbps) o cuando hay múltiples usuarios en la misma red corporativa usando Copilot simultáneamente.

**Solución:**
```
Opción A — Reducir el alcance del prompt (recomendada):
En lugar de solicitar las 4 correlaciones en un solo prompt, 
divide la solicitud en prompts individuales:
  Prompt 1: "Calcula el coeficiente de correlación de Pearson 
             entre Duracion_Min y Temperatura_C"
  Prompt 2: "Calcula el coeficiente de correlación de Pearson 
             entre Duracion_Min y Velocidad_RPM"
  [Repite para Presion_Bar y Humedad_Pct]
  Prompt 5: "Con los valores de correlación que calculaste, 
             crea la tabla resumen comparativa"

Opción B — Usar fórmulas de Excel directamente:
Si Copilot no responde, calcula las correlaciones manualmente:
  =COEF.DE.CORREL(TablaParadas[Duracion_Min], 
                  TablaParadas[Temperatura_C])
  [Repite para cada variable]
Luego usa Copilot solo para la interpretación de los resultados.

Opción C — Usar Copilot Chat (copilot.microsoft.com):
Copia y pega los datos de correlación calculados en Excel 
hacia Copilot Chat para obtener la interpretación analítica 
sin depender de la integración de Copilot en Excel.

Verificación de conectividad:
  - Abre speedtest.net y verifica velocidad > 10 Mbps.
  - Si estás en WiFi, intenta conectarte por cable Ethernet.
  - Cierra otras aplicaciones que consuman ancho de banda 
    (Teams con video, OneDrive sincronizando archivos grandes).
```

---

## Limpieza del Entorno

Al finalizar la práctica, realiza las siguientes acciones para dejar el entorno ordenado y listo para la Práctica 6:

### Organización de Archivos en OneDrive

```
1. Verifica que los siguientes archivos estén en la carpeta /Practica5/:
   - dataset_paradas_proceso_P5.xlsx        ✓
   - matriz_riesgos_P5_actualizada.xlsx     ✓
   - Resumen_Ejecutivo_Analisis_Paradas_P5.docx ✓

2. Elimina archivos temporales o copias duplicadas:
   - Si creaste versiones de prueba (ej. "Copia de..."), elimínalas.
   - Vacía la papelera de OneDrive si hay archivos eliminados.

3. Comparte los entregables con el instructor (si se requiere):
   OneDrive → clic derecho en carpeta /Practica5/ 
   → Compartir → Escribe el correo del instructor 
   → Permiso: "Puede ver" → Enviar
```

### Cierre de Aplicaciones

```
1. Guarda y cierra dataset_paradas_proceso_P5.xlsx (Ctrl+S → Ctrl+W).
2. Guarda y cierra matriz_riesgos_P5_actualizada.xlsx (Ctrl+S → Ctrl+W).
3. Guarda y cierra Resumen_Ejecutivo_Analisis_Paradas_P5.docx (Ctrl+S → Ctrl+W).
4. Cierra la pestaña de Copilot Chat en el navegador.
5. Verifica que OneDrive muestre estado "Sincronización completada" 
   (ícono verde en bandeja del sistema) antes de cerrar sesión.
```

### Preparación para la Práctica 6

```
Los siguientes archivos de esta práctica serán insumos para la Práctica 6:
- dataset_paradas_proceso_P5.xlsx (especialmente hoja Plan_Planeacion_Optimizado)
- matriz_riesgos_P5_actualizada.xlsx
- Resumen_Ejecutivo_Analisis_Paradas_P5.docx

Asegúrate de que estén completamente guardados y sincronizados 
en OneDrive antes de la siguiente sesión.
```

---

## Resumen

### Lo que Construiste en Esta Práctica

En esta práctica de 90 minutos aplicaste un ciclo analítico completo de datos operativos de planta, pasando de datos crudos de paradas a decisiones de planeación documentadas y accionables:

| Actividad                         | Herramienta Principal     | Competencia Desarrollada                          |
|-----------------------------------|---------------------------|---------------------------------------------------|
| Exploración y limpieza del dataset | Copilot en Excel          | Evaluación crítica de calidad de datos            |
| Pareto por Causa Principal        | Copilot en Excel           | Identificación de causas raíz de mayor impacto    |
| Paretos por Equipo y Turno        | Copilot en Excel           | Análisis multicapa y cruzado de datos             |
| Correlación de variables          | Copilot en Excel + Chat    | Detección de relaciones causa-efecto ocultas      |
| Actualización de matriz de riesgos| Copilot en Excel           | Gestión de riesgos basada en datos reales         |
| Plan de planeación optimizado     | Copilot en Excel           | Traducción de insights en acciones de planeación  |
| Resumen ejecutivo                 | Copilot en Word            | Comunicación ejecutiva de hallazgos analíticos    |

### Conceptos Clave Reforzados

- **Ciclo virtuoso del Capítulo 5:** Los hallazgos del análisis de correlación (Lección 5.2) se tradujeron directamente en el plan de planeación optimizado (Lección 5.3), cerrando el loop de mejora continua.
- **Diferencia entre correlación y causalidad:** Identificaste correlaciones estadísticas pero reconociste la necesidad de validación operativa antes de establecer causalidad.
- **Conocimiento tácito → explícito:** Los patrones que "se sabían" en planta (como la relación entre temperatura y duración de paradas) fueron documentados, cuantificados y traducidos en umbrales de alerta accionables.
- **Copilot como intermediario analítico:** No fue necesario conocimiento avanzado de estadística ni programación; Copilot actuó como el puente entre los datos operativos y las decisiones de gestión.

### Recursos Adicionales

- [Documentación oficial de Copilot en Excel — Microsoft Learn](https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-overview)
- [Análisis de Pareto en manufactura — ASQ Quality Tools](https://asq.org/quality-resources/pareto)
- [Correlación estadística en procesos industriales — NIST/SEMATECH e-Handbook](https://www.itl.nist.gov/div898/handbook/pmc/section4/pmc4.htm)
- [Gestión de riesgos operativos en manufactura — ISO 31000:2018](https://www.iso.org/iso-31000-risk-management.html)
- [Optimización de planeación de producción con IA — MIT Sloan Management Review](https://sloanreview.mit.edu/article/how-ai-is-transforming-manufacturing-planning/)

> 💡 **Recuerda:** Las respuestas de Copilot son generativas y pueden variar entre sesiones. Los resultados obtenidos en esta práctica son referenciales. Siempre evalúa críticamente los outputs de Copilot contrastándolos con tu conocimiento operativo de planta antes de tomar decisiones basadas en ellos.

---
