# Práctica 6 — Despliegue de "Ishikawa" y "5 Porqués" con Copilot Chat

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Crear |
| **Módulo / Capítulo** | Capítulo 6 — Análisis de Causa Raíz (RCA) asistido por IA |
| **ID de práctica** | 06-00-01 |

---

## 2. Descripción General

En esta práctica aplicarás la metodología completa de Análisis de Causa Raíz (RCA) sobre tres casos de falla documentados de manufactura —uno de calidad, uno de mantenimiento y uno de producción— utilizando Microsoft Copilot Chat como facilitador analítico. Para cada caso construirás el esquema del diagrama de Ishikawa con las 6M, profundizarás en la causa raíz mediante el método conversacional de los 5 Porqués, evaluarás la solidez de las contramedidas propuestas y documentarás el análisis completo en un reporte Word listo para auditorías de calidad. La práctica refuerza el enfoque preventivo y predictivo que distingue a los equipos de manufactura de clase mundial, integrando el juicio experto del participante con las capacidades analíticas de la inteligencia artificial.

---

## 3. Objetivos de Aprendizaje

Al finalizar esta práctica serás capaz de:

- [ ] Construir el esquema de un diagrama de Ishikawa (6M) para problemas de manufactura utilizando prompts estructurados en Copilot Chat.
- [ ] Ejecutar el análisis de 5 Porqués de forma conversacional con Copilot, identificando la causa raíz real de cada falla y diferenciándola de los síntomas superficiales.
- [ ] Evaluar la eficacia, viabilidad operativa y permanencia de contramedidas propuestas con apoyo de Copilot, identificando brechas lógicas en el análisis.
- [ ] Generar un reporte RCA estructurado en Microsoft Word con Copilot, que incluya diagrama, análisis de causas, contramedidas y plan de seguimiento, listo para uso en auditorías de calidad.

---

## 4. Prerrequisitos

### 4.1 Conocimientos Previos

- Comprensión conceptual de las metodologías Ishikawa (diagrama de causa-efecto) y 5 Porqués.
- Familiaridad con los datos operativos de calidad, mantenimiento y producción trabajados en las Prácticas 1 a 5 del curso (o revisión del resumen provisto por el instructor).
- Experiencia básica en la formulación de prompts en Copilot Chat (Prácticas anteriores).
- Conocimiento del enfoque RCA descrito en la Lección 6.1: propósito, etapas y rol amplificador de Copilot.

### 4.2 Accesos y Recursos Requeridos

| Recurso | Estado requerido |
|---|---|
| Cuenta corporativa Microsoft 365 con licencia **Copilot activa** | ✅ Verificado antes del inicio |
| Acceso a **copilot.microsoft.com** en modo **Work** (cuenta corporativa) | ✅ Sesión iniciada |
| Microsoft Word (versión 2308 o posterior) con Copilot habilitado | ✅ Disponible |
| Archivo **`casos_RCA_manufactura.docx`** en OneDrive for Business | ✅ Descargado o sincronizado |
| Conexión a internet estable ≥ 10 Mbps | ✅ Verificada |
| Almacenamiento disponible ≥ 500 MB en OneDrive | ✅ Confirmado |

> ⚠️ **Nota de privacidad:** Asegúrate de estar usando Copilot Chat en **modo Work** (copilot.microsoft.com con tu cuenta corporativa). Los datos de esta práctica son simulados. **No cargues datos reales de producción sin verificar el modo de protección activo.**

---

## 5. Entorno de Laboratorio

### 5.1 Hardware Recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8va gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Resolución de pantalla | 1366 × 768 | 1920 × 1080 |
| Conexión a internet | 10 Mbps | Red cableada corporativa |
| Almacenamiento libre | 5 GB | 10 GB |

### 5.2 Software y Aplicaciones

| Aplicación | Versión mínima | Uso en esta práctica |
|---|---|---|
| Microsoft 365 Copilot | Licencia 2024 o posterior | Análisis RCA conversacional |
| Copilot Chat (Web) | copilot.microsoft.com | Ishikawa, 5 Porqués, validación |
| Microsoft Word | M365 Apps v2308+ | Generación del reporte RCA |
| OneDrive for Business | Incluido en M365 | Acceso al archivo de casos |
| Microsoft Teams | New Teams v2.0+ | Opcional: colaboración en equipo |

### 5.3 Configuración Inicial del Entorno

Antes de comenzar los pasos del laboratorio, ejecuta la siguiente lista de verificación:

**Paso A — Verificar modo Work en Copilot Chat:**

1. Abre tu navegador y dirígete a `https://copilot.microsoft.com`.
2. Inicia sesión con tu **cuenta corporativa** (formato: `usuario@empresa.com`).
3. Verifica que en la parte superior aparezca tu nombre corporativo y el indicador **"Work"** o **"Trabajo"** activo. Si ves "Personal", cierra sesión y vuelve a ingresar con la cuenta corporativa.

**Paso B — Verificar acceso al archivo de casos:**

1. Abre OneDrive for Business desde `https://onedrive.live.com` o desde el explorador de archivos.
2. Navega a la carpeta del curso y confirma que el archivo **`casos_RCA_manufactura.docx`** esté disponible.
3. Si el archivo no está disponible, solicita al instructor la versión pre-completada antes de continuar.

**Paso C — Abrir Word con Copilot:**

1. Abre Microsoft Word desde el menú de aplicaciones de Microsoft 365.
2. Crea un nuevo documento en blanco y guárdalo en OneDrive con el nombre:
   `RCA_Completo_[TuNombre]_[Fecha].docx`
   Ejemplo: `RCA_Completo_JuanPerez_2025-01-15.docx`
3. Verifica que el ícono de Copilot (estrella de cuatro puntas) esté visible en la cinta de opciones o en el panel lateral derecho.

---

## 6. Procedimiento Paso a Paso

> 📌 **Nota sobre variabilidad de Copilot:** Las respuestas de Copilot son generativas y pueden variar entre sesiones. Los resultados mostrados en esta guía son **referenciales**. Evalúa críticamente cada respuesta antes de incorporarla a tu análisis. Si una respuesta no parece precisa o relevante, reformula el prompt con más contexto.

---

### Paso 1 — Revisión de los Casos de Falla

**Objetivo:** Familiarizarte con los tres casos documentados antes de iniciar el análisis con Copilot, identificando el efecto (problema) de cada caso con precisión.

#### Instrucciones:

1. Abre el archivo **`casos_RCA_manufactura.docx`** desde OneDrive.

2. Lee detenidamente los tres casos documentados. A continuación se presenta un resumen de referencia para esta práctica:

   **Caso 1 — Calidad:** *Defecto de pintura en panel lateral de carrocería*
   - Descripción: El 12% de los paneles laterales inspeccionados en la línea de pintura presentan burbujas superficiales en la capa de acabado. El defecto apareció por primera vez hace 6 semanas y se ha repetido en los tres últimos lotes de producción.
   - Impacto: Retrabajo estimado de 4.2 horas/panel, costo adicional de $180 USD/unidad.

   **Caso 2 — Mantenimiento:** *Paro no programado de compresor de aire en área de ensamble*
   - Descripción: El compresor principal del área de ensamble ha presentado 4 paros no programados en los últimos 30 días, cada uno con una duración promedio de 2.5 horas. El equipo tiene 7 años de operación.
   - Impacto: Pérdida de producción estimada en 340 unidades/mes, costo de mantenimiento correctivo de $2,400 USD/paro.

   **Caso 3 — Producción:** *Baja eficiencia en línea de ensamble de sub-componentes eléctricos*
   - Descripción: La línea de ensamble de arneses eléctricos opera al 67% de su capacidad instalada (meta: 88%). La caída comenzó tras la rotación de turno ocurrida hace 8 semanas.
   - Impacto: Déficit de 210 arneses/semana respecto a la meta de producción.

3. En tu documento Word `RCA_Completo_[TuNombre]_[Fecha].docx`, crea una sección de título con el formato:

   ```
   REPORTE DE ANÁLISIS DE CAUSA RAÍZ (RCA)
   Planta: [Nombre de tu planta o "Planta Simulada Curso M365"]
   Fecha: [Fecha actual]
   Analista: [Tu nombre]
   ```

4. Debajo del encabezado, crea tres secciones numeradas: **Caso 1: Calidad**, **Caso 2: Mantenimiento**, **Caso 3: Producción**.

#### Resultado Esperado:
- Documento Word abierto con estructura de tres casos listos para ser completados.
- Comprensión clara del efecto (problema observable) de cada caso antes de iniciar el análisis.

#### Verificación:
- [ ] El documento Word está guardado en OneDrive con el nombre correcto.
- [ ] Las tres secciones de casos están creadas en el documento.
- [ ] Puedes describir con tus propias palabras el problema de cada caso sin releer el archivo.

---

### Paso 2 — Construcción del Diagrama de Ishikawa con Copilot Chat (Caso 1: Calidad)

**Objetivo:** Utilizar Copilot Chat para generar el esquema del diagrama de Ishikawa con las 6M para el defecto de pintura, identificando las posibles causas en cada categoría.

#### Instrucciones:

1. Abre **Copilot Chat** en `https://copilot.microsoft.com` y verifica que estás en **modo Work**.

2. Inicia una nueva conversación haciendo clic en **"Nueva conversación"** (ícono de lápiz o botón correspondiente).

3. Escribe el siguiente prompt inicial en el cuadro de texto y presiona **Enter**:

   ```
   Actúa como un ingeniero de calidad con experiencia en manufactura automotriz 
   especializado en Análisis de Causa Raíz (RCA). Voy a describirte un problema 
   de calidad y necesito que construyas el esquema completo de un diagrama de 
   Ishikawa (diagrama de causa-efecto) utilizando las 6M: Mano de obra, Máquina, 
   Método, Material, Medio ambiente y Medición.

   PROBLEMA (EFECTO): El 12% de los paneles laterales de carrocería inspeccionados 
   en la línea de pintura presentan burbujas superficiales en la capa de acabado. 
   El defecto se ha repetido en los tres últimos lotes de producción durante las 
   últimas 6 semanas.

   Para cada una de las 6M, proporciona entre 3 y 5 posibles causas específicas 
   y relevantes para este tipo de defecto en un proceso de pintura industrial. 
   Organiza la respuesta en formato de tabla con columnas: Categoría (M), 
   Causa posible, Descripción breve. Sé específico y técnico.
   ```

4. Lee cuidadosamente la respuesta de Copilot. Evalúa si las causas propuestas son técnicamente coherentes con un proceso de pintura industrial.

5. Si alguna categoría tiene causas genéricas o poco específicas, formula un **prompt de refinamiento**:

   ```
   Las causas en la categoría [nombre de la categoría, ej: "Máquina"] son 
   demasiado genéricas para un proceso de pintura por electroforesis/aplicación 
   de pintura en cabina. Por favor, reemplázalas por causas más específicas 
   considerando equipos como pistolas de aspersión, sistemas de filtración de 
   aire, hornos de curado y transportadores de cadena.
   ```

6. Una vez que tengas el esquema completo y validado, copia el contenido de la tabla y pégalo en la sección **"Caso 1: Calidad"** de tu documento Word.

7. Agrega un encabezado sobre la tabla: **"Diagrama de Ishikawa — Análisis de Causas Potenciales"**.

#### Resultado Esperado (Referencial):

La respuesta de Copilot debe generar una tabla similar a la siguiente estructura:

| Categoría (M) | Causa posible | Descripción breve |
|---|---|---|
| Mano de obra | Técnica incorrecta de aplicación | El operador no mantiene la distancia y ángulo estándar de la pistola de aspersión |
| Mano de obra | Falta de capacitación en nuevo material | Rotación reciente de personal sin entrenamiento en el nuevo proveedor de pintura |
| Máquina | Presión irregular en pistola de aspersión | Variación de ±15 PSI por encima del rango especificado (40-60 PSI) |
| Máquina | Filtros de cabina saturados | Filtros con más de 800 horas de operación sin reemplazo (límite: 600 h) |
| Método | Ausencia de control de temperatura previa | No se verifica la temperatura superficial del panel antes de aplicar la primera capa |
| Material | Viscosidad fuera de especificación | Lote de pintura recibido con viscosidad 18% superior al parámetro de proceso |
| Medio ambiente | Humedad relativa elevada en cabina | Humedad >75% registrada en los tres turnos donde ocurrió el defecto |
| Medición | Calibración vencida del viscosímetro | Último registro de calibración data de 4 meses (frecuencia requerida: mensual) |

> ⚠️ **Recuerda:** Tu tabla puede diferir de este ejemplo. Lo importante es que las causas sean técnicamente plausibles y específicas para el proceso de pintura.

#### Verificación:
- [ ] La tabla del diagrama Ishikawa tiene las 6 categorías (6M) con al menos 3 causas cada una.
- [ ] Las causas son específicas para el proceso de pintura (no genéricas).
- [ ] La tabla está copiada en el documento Word en la sección Caso 1.

---

### Paso 3 — Análisis de 5 Porqués con Copilot Chat (Caso 1: Calidad)

**Objetivo:** Profundizar en la causa más probable identificada en el Ishikawa mediante el método conversacional de los 5 Porqués, llegando a la causa raíz real.

#### Instrucciones:

1. En la **misma conversación** de Copilot Chat (para mantener el contexto del Caso 1), escribe el siguiente prompt:

   ```
   Basándote en el diagrama de Ishikawa que acabamos de construir, identifica 
   la causa más probable que explique el defecto de burbujas en la pintura 
   considerando que el defecto comenzó hace 6 semanas y coincide con la llegada 
   de un nuevo lote de material. Ahora aplica el método de los 5 Porqués 
   comenzando desde esa causa. 

   Formato requerido:
   - Síntoma/Efecto: [descripción del problema]
   - ¿Por qué 1?: [causa de primer nivel] → Evidencia o dato que lo sustenta
   - ¿Por qué 2?: [causa de segundo nivel] → Evidencia o dato que lo sustenta
   - ¿Por qué 3?: [causa de tercer nivel] → Evidencia o dato que lo sustenta
   - ¿Por qué 4?: [causa de cuarto nivel] → Evidencia o dato que lo sustenta
   - ¿Por qué 5?: [CAUSA RAÍZ] → Evidencia o dato que lo sustenta
   - Causa Raíz Identificada: [declaración clara y accionable]
   ```

2. Revisa la cadena de los 5 Porqués generada por Copilot. Verifica que cada "porqué" sea una causa directa del nivel anterior (no un salto lógico).

3. Si identificas un salto lógico o una respuesta que no tiene sustento, usa el siguiente **prompt de validación lógica**:

   ```
   En el paso [número del porqué], la conexión causal entre "[causa anterior]" 
   y "[causa siguiente]" no parece directa. ¿Existe un paso intermedio que 
   explique mejor esa relación? Por favor, revisa la cadena y propón una 
   versión corregida que sea lógicamente consistente.
   ```

4. Una vez que la cadena de 5 Porqués sea lógicamente sólida, copia el análisis completo en el documento Word, debajo de la tabla de Ishikawa del Caso 1.

5. Agrega el encabezado: **"Análisis de 5 Porqués — Causa Raíz Identificada"**.

#### Resultado Esperado (Referencial):

```
Síntoma/Efecto: Burbujas superficiales en capa de acabado de paneles laterales (12% de incidencia)

¿Por qué 1?: La viscosidad de la pintura aplicada está fuera del rango especificado
→ Evidencia: Registros del laboratorio de calidad muestran viscosidad 18% superior en el lote actual

¿Por qué 2?: El lote de pintura recibido no fue rechazado en la inspección de entrada
→ Evidencia: El registro de recepción no incluye medición de viscosidad como parámetro de aceptación

¿Por qué 3?: El procedimiento de inspección de recepción de materiales no especifica la viscosidad como criterio de aceptación/rechazo
→ Evidencia: Revisión del procedimiento PR-MAT-012 confirmó ausencia del parámetro

¿Por qué 4?: El procedimiento PR-MAT-012 no fue actualizado cuando se cambió el proveedor de pintura hace 4 meses
→ Evidencia: La última revisión del procedimiento data de 18 meses antes del cambio de proveedor

¿Por qué 5?: No existe un proceso formal de actualización de procedimientos de inspección cuando se realizan cambios de proveedor de materiales críticos
→ Evidencia: Ausencia de registro de cambio de proveedor vinculado al sistema de gestión de procedimientos

CAUSA RAÍZ IDENTIFICADA: La organización carece de un proceso formal que vincule los cambios de proveedor de materiales críticos con la actualización de los criterios de inspección de recepción correspondientes.
```

#### Verificación:
- [ ] La cadena de 5 Porqués tiene exactamente 5 niveles con conexión causal lógica entre cada uno.
- [ ] La causa raíz identificada es sistémica (no apunta a un error individual de operador).
- [ ] El análisis está documentado en el documento Word.

---

### Paso 4 — Ishikawa y 5 Porqués para Caso 2 (Mantenimiento) y Caso 3 (Producción)

**Objetivo:** Aplicar el mismo proceso de los Pasos 2 y 3 a los casos de mantenimiento y producción, desarrollando fluidez en la formulación de prompts para distintos contextos operativos.

#### Instrucciones:

1. **Para el Caso 2 — Mantenimiento (Paro de compresor):**

   Inicia una **nueva conversación** en Copilot Chat y usa el siguiente prompt base, adaptándolo al caso de mantenimiento:

   ```
   Actúa como un ingeniero de mantenimiento industrial con experiencia en 
   análisis de fallas de equipos rotativos y sistemas de aire comprimido. 
   
   PROBLEMA (EFECTO): Un compresor de aire de 7 años de operación en el área 
   de ensamble ha presentado 4 paros no programados en los últimos 30 días, 
   cada uno con duración promedio de 2.5 horas.

   Paso 1: Construye el diagrama de Ishikawa con las 6M (Mano de obra, Máquina, 
   Método, Material, Medio ambiente, Medición) con 3-5 causas específicas por 
   categoría para este tipo de falla en equipos de aire comprimido industrial. 
   Usa formato de tabla.

   Paso 2: Identifica la causa más probable considerando la antigüedad del equipo 
   (7 años) y la frecuencia creciente de paros, y aplica el método de 5 Porqués 
   con el formato: Síntoma → Por qué 1 → Por qué 2 → Por qué 3 → Por qué 4 → 
   Por qué 5 → Causa Raíz.
   ```

2. Evalúa la respuesta. Si las causas del Ishikawa son genéricas para un compresor industrial, refina con:

   ```
   Sé más específico para un compresor de tornillo rotativo de 75 HP. 
   Considera componentes como: separador de aceite, válvulas de mínima presión, 
   sistema de refrigeración, filtros de aire de entrada y controles electrónicos.
   ```

3. Copia el Ishikawa y los 5 Porqués del Caso 2 en el documento Word, en la sección **"Caso 2: Mantenimiento"**.

4. **Para el Caso 3 — Producción (Baja eficiencia en línea de arneses):**

   Inicia una **nueva conversación** en Copilot Chat y usa el siguiente prompt:

   ```
   Actúa como un ingeniero de manufactura especializado en mejora continua 
   y análisis de eficiencia de líneas de ensamble manual.

   PROBLEMA (EFECTO): La línea de ensamble de arneses eléctricos opera al 67% 
   de su capacidad instalada cuando la meta es 88%. La caída de eficiencia 
   comenzó hace 8 semanas, coincidiendo con una rotación de turno.

   Paso 1: Construye el diagrama de Ishikawa con las 6M para este problema 
   de eficiencia. Considera que es una línea de ensamble manual con 12 
   operadores, balanceo de línea establecido y tiempos estándar definidos. 
   Usa formato de tabla con 3-5 causas por categoría.

   Paso 2: Dado que el problema coincide con una rotación de turno hace 8 semanas, 
   aplica el método de 5 Porqués enfocado en esa correlación temporal. 
   Usa el formato estándar de 5 niveles con causa raíz identificada al final.
   ```

5. Copia el Ishikawa y los 5 Porqués del Caso 3 en el documento Word, en la sección **"Caso 3: Producción"**.

#### Resultado Esperado:
- Tres análisis completos (Ishikawa + 5 Porqués) documentados en el Word, uno por cada caso.
- Las causas raíz de los tres casos son sistémicas y diferentes entre sí (no repetitivas).

#### Verificación:
- [ ] El documento Word tiene los análisis completos de los tres casos.
- [ ] Cada caso tiene su tabla Ishikawa (6M) y su cadena de 5 Porqués.
- [ ] Las causas raíz identificadas son distintas y específicas para cada tipo de problema (calidad, mantenimiento, producción).

---

### Paso 5 — Propuesta y Validación de Contramedidas con Copilot

**Objetivo:** Generar contramedidas para la causa raíz de cada caso y usar Copilot para evaluar su solidez lógica, viabilidad operativa y permanencia (que el problema no regrese).

#### Instrucciones:

1. Para cada uno de los tres casos, en la conversación de Copilot correspondiente (o en una nueva si la sesión expiró), usa el siguiente **prompt de generación de contramedidas**:

   **Para el Caso 1 (adapta el texto de causa raíz según tu análisis):**

   ```
   La causa raíz identificada para el defecto de pintura es: "La organización 
   carece de un proceso formal que vincule los cambios de proveedor de materiales 
   críticos con la actualización de los criterios de inspección de recepción 
   correspondientes."

   Por favor, propón 3 contramedidas específicas para eliminar esta causa raíz. 
   Para cada contramedida incluye:
   - Descripción de la acción
   - Responsable sugerido (rol/área)
   - Plazo de implementación (inmediato <2 semanas / corto plazo 2-8 semanas / 
     mediano plazo 2-6 meses)
   - Indicador de seguimiento (cómo saber que funcionó)
   - Tipo: Correctiva (elimina la causa) vs. Preventiva (evita recurrencia)

   Presenta la respuesta en formato de tabla.
   ```

2. Repite el prompt anterior para los Casos 2 y 3, reemplazando la causa raíz con la identificada en el análisis correspondiente.

3. Una vez que tengas las contramedidas propuestas por Copilot para los tres casos, aplica el siguiente **prompt de validación de permanencia** para cada caso:

   ```
   Ahora actúa como auditor de calidad. Evalúa las 3 contramedidas propuestas 
   para el [Caso 1/2/3] y responde las siguientes preguntas para cada una:

   1. ¿Esta contramedida ataca la causa raíz identificada o solo un síntoma? 
      (Sí/No + justificación)
   2. ¿Existe alguna condición bajo la cual el problema podría reaparecer 
      aunque esta contramedida esté implementada? (Sí/No + descripción del riesgo)
   3. ¿La contramedida es sostenible sin supervisión constante? 
      (Sí/No + justificación)
   4. ¿Hay alguna brecha lógica entre la causa raíz y la acción propuesta? 
      (Sí/No + descripción)

   Concluye con una recomendación: ¿Cuál de las 3 contramedidas tiene mayor 
   probabilidad de permanencia y por qué?
   ```

4. Revisa el análisis de Copilot. Si identifica brechas en alguna contramedida, solicita una versión mejorada:

   ```
   La contramedida [número] tiene la siguiente brecha identificada: [descripción]. 
   Por favor, propón una versión mejorada de esa contramedida que cierre esa brecha 
   y tenga mayor probabilidad de permanencia.
   ```

5. Copia las tablas de contramedidas validadas en el documento Word, en la sección correspondiente a cada caso, con el encabezado: **"Contramedidas Propuestas y Evaluación de Permanencia"**.

#### Resultado Esperado (Referencial — Caso 1):

| # | Contramedida | Responsable | Plazo | Indicador | Tipo |
|---|---|---|---|---|---|
| 1 | Actualizar procedimiento PR-MAT-012 para incluir viscosidad como criterio de aceptación/rechazo en recepción de pintura | Ing. de Calidad + Compras | Inmediato (<2 sem) | % de lotes de pintura con medición de viscosidad en recepción = 100% | Correctiva |
| 2 | Crear proceso formal de "Cambio de Proveedor" que incluya revisión y actualización de procedimientos de inspección afectados | Gerencia de Calidad + Compras | Corto plazo (4-6 sem) | # de cambios de proveedor con procedimientos actualizados / total de cambios = 100% | Preventiva |
| 3 | Implementar alerta automática en sistema ERP que notifique a Calidad cuando se registre un nuevo proveedor de material crítico | TI + Calidad | Mediano plazo (3-4 meses) | # de alertas generadas vs. # de cambios de proveedor registrados = 100% | Preventiva |

#### Verificación:
- [ ] Cada caso tiene al menos 3 contramedidas con los 5 campos requeridos (descripción, responsable, plazo, indicador, tipo).
- [ ] Copilot evaluó la permanencia de cada contramedida e identificó al menos una brecha en alguno de los casos.
- [ ] Las contramedidas validadas están documentadas en el Word.

---

### Paso 6 — Generación del Reporte RCA Completo en Word con Copilot

**Objetivo:** Usar Copilot en Word para estructurar, completar y dar formato profesional al reporte RCA completo, listo para uso en auditorías de calidad.

#### Instrucciones:

1. Abre tu documento Word `RCA_Completo_[TuNombre]_[Fecha].docx` en Microsoft Word.

2. Verifica que tienes el contenido de los pasos anteriores pegado en las tres secciones. El documento debe tener al menos:
   - Encabezado del reporte
   - Caso 1: Ishikawa + 5 Porqués + Contramedidas
   - Caso 2: Ishikawa + 5 Porqués + Contramedidas
   - Caso 3: Ishikawa + 5 Porqués + Contramedidas

3. Activa el panel de Copilot en Word haciendo clic en el ícono de Copilot en la cinta de opciones (pestaña **Home** o **Inicio**, grupo Copilot) o usando el atajo `Alt + I` si está disponible en tu versión.

4. En el panel de Copilot de Word, escribe el siguiente prompt:

   ```
   Este documento contiene el análisis RCA de tres casos de manufactura. 
   Por favor, realiza las siguientes mejoras al documento:

   1. Agrega una sección de "Resumen Ejecutivo" al inicio del documento (antes 
      de los casos) que sintetice en máximo 200 palabras: los tres problemas 
      analizados, las tres causas raíz identificadas y el total de contramedidas 
      propuestas con su distribución por tipo (correctivas vs. preventivas).

   2. Para cada uno de los tres casos, agrega una subsección de "Plan de 
      Seguimiento" con formato de tabla que incluya: Contramedida, Fecha límite 
      de implementación, Responsable, Evidencia de cierre requerida y Estado 
      (Pendiente/En proceso/Cerrada).

   3. Agrega una sección final de "Lecciones Aprendidas" con 3 puntos clave 
      que apliquen transversalmente a los tres casos analizados.

   4. Aplica el estilo de documento "Profesional" con encabezados numerados, 
      tabla de contenido al inicio y numeración de páginas.
   ```

5. Revisa los cambios propuestos por Copilot en Word. Acepta los que consideres correctos y rechaza o modifica los que no sean precisos.

6. Si el Resumen Ejecutivo generado por Copilot contiene información incorrecta o no alineada con tu análisis, corrígelo manualmente o usa un prompt de refinamiento:

   ```
   El resumen ejecutivo menciona [dato incorrecto]. Por favor, corrígelo 
   indicando que [dato correcto] según el análisis documentado en el cuerpo 
   del reporte.
   ```

7. Guarda el documento. Asegúrate de que esté sincronizado en OneDrive (ícono de nube verde en la barra de título).

8. **Opcional — Compartir en Teams:** Si estás trabajando en equipo, comparte el documento desde Word usando **Compartir > Copiar vínculo** y pega el enlace en el canal de Teams del curso para revisión del instructor.

#### Resultado Esperado:
El documento Word final debe contener:
- ✅ Portada / encabezado del reporte
- ✅ Tabla de contenido
- ✅ Resumen ejecutivo (≤200 palabras)
- ✅ Caso 1: Ishikawa + 5 Porqués + Contramedidas + Plan de seguimiento
- ✅ Caso 2: Ishikawa + 5 Porqués + Contramedidas + Plan de seguimiento
- ✅ Caso 3: Ishikawa + 5 Porqués + Contramedidas + Plan de seguimiento
- ✅ Sección de Lecciones Aprendidas (3 puntos)
- ✅ Numeración de páginas

#### Verificación:
- [ ] El documento tiene todas las secciones listadas arriba.
- [ ] El Resumen Ejecutivo refleja con precisión el contenido del análisis (no contiene datos inventados por Copilot).
- [ ] El documento está guardado y sincronizado en OneDrive.
- [ ] Los planes de seguimiento tienen fechas límite y responsables definidos.

---

### Paso 7 — Reflexión Crítica: Evaluación de la Calidad del Análisis

**Objetivo:** Usar Copilot Chat para evaluar la calidad global del análisis RCA realizado, identificar posibles brechas metodológicas y consolidar el aprendizaje.

#### Instrucciones:

1. Abre una **nueva conversación** en Copilot Chat.

2. Escribe el siguiente prompt de autoevaluación:

   ```
   Actúa como un consultor experto en metodologías de mejora continua 
   (Six Sigma Black Belt / AIAG-VDA). Voy a describirte el proceso de análisis 
   RCA que realicé para tres casos de manufactura y necesito que evalúes la 
   calidad metodológica del análisis.

   Los tres análisis siguieron este proceso:
   1. Construcción de diagrama Ishikawa con 6M (3-5 causas por categoría)
   2. Selección de causa más probable basada en correlación temporal con datos
   3. Aplicación de 5 Porqués con cadena causal lógica
   4. Identificación de causa raíz sistémica (no individual)
   5. Propuesta de 3 contramedidas por caso (correctivas y preventivas)
   6. Validación de permanencia de contramedidas

   Por favor, evalúa este proceso respondiendo:
   a) ¿Qué elementos del proceso son metodológicamente sólidos según los 
      estándares AIAG y ASQ para RCA en manufactura?
   b) ¿Qué pasos críticos del RCA podrían estar ausentes en este proceso 
      que podrían comprometer la calidad del análisis?
   c) ¿Cómo podría Copilot haber introducido sesgos o limitaciones en el 
      análisis que el equipo humano debe verificar?
   d) ¿Qué recomendarías para fortalecer este proceso en una implementación 
      real en planta?
   ```

3. Lee la evaluación de Copilot. Identifica al menos **dos puntos de mejora** que puedas aplicar si repites el análisis en tu planta real.

4. En el documento Word, agrega una sección final llamada **"Notas de Mejora del Proceso RCA"** y documenta los dos puntos de mejora identificados en lenguaje propio (no copiar y pegar la respuesta de Copilot directamente).

5. Guarda el documento final.

#### Resultado Esperado:
- Evaluación crítica del proceso RCA realizado, con identificación de fortalezas y áreas de mejora.
- Comprensión de las limitaciones de Copilot como herramienta de análisis (posibles sesgos, falta de datos reales, etc.).
- Sección de mejoras documentada en Word con reflexión propia del participante.

#### Verificación:
- [ ] El participante puede nombrar al menos dos limitaciones del uso de Copilot en el proceso RCA.
- [ ] La sección "Notas de Mejora del Proceso RCA" está escrita en lenguaje propio (no es copia directa de Copilot).
- [ ] El documento final está guardado en OneDrive.

---

## 7. Validación y Pruebas

Al finalizar todos los pasos, realiza la siguiente verificación integral del entregable:

### Lista de Verificación del Entregable Final

| Criterio | Indicador de cumplimiento | ¿Cumple? |
|---|---|---|
| **Cobertura de casos** | Los tres casos (calidad, mantenimiento, producción) están analizados | ☐ |
| **Ishikawa completo** | Cada caso tiene las 6M con mínimo 3 causas específicas por categoría | ☐ |
| **5 Porqués lógicos** | Cada caso tiene 5 niveles causales con conexión lógica directa entre ellos | ☐ |
| **Causa raíz sistémica** | Las causas raíz identificadas son sistémicas (no apuntan a error humano individual) | ☐ |
| **Contramedidas validadas** | Cada caso tiene mínimo 3 contramedidas con evaluación de permanencia | ☐ |
| **Plan de seguimiento** | Cada caso tiene tabla de seguimiento con fechas, responsables y evidencias | ☐ |
| **Resumen ejecutivo** | Existe un resumen ejecutivo de máximo 200 palabras al inicio del documento | ☐ |
| **Lecciones aprendidas** | La sección final tiene 3 lecciones transversales | ☐ |
| **Formato profesional** | El documento tiene tabla de contenido, encabezados numerados y paginación | ☐ |
| **Guardado en OneDrive** | El archivo está sincronizado en OneDrive (ícono verde confirmado) | ☐ |
| **Reflexión crítica** | La sección de mejoras refleja pensamiento propio del participante | ☐ |

### Prueba de Calidad del Análisis

Para verificar que el análisis RCA es metodológicamente sólido, responde las siguientes preguntas sin consultar el documento:

1. ¿Cuál es la causa raíz del Caso 1 (defecto de pintura)? ¿Es sistémica o individual?
2. ¿Qué distingue a una contramedida **correctiva** de una **preventiva** en el contexto de tu análisis?
3. ¿En cuál de los tres casos identificó Copilot la mayor cantidad de brechas en las contramedidas propuestas? ¿Por qué?
4. ¿Qué limitación de Copilot identificaste en el Paso 7 que deberías considerar al usar esta herramienta en tu planta real?

> Si puedes responder estas cuatro preguntas con claridad y sin consultar el documento, has alcanzado el nivel **Crear** de la taxonomía de Bloom para esta práctica.

---

## 8. Solución de Problemas

### Problema 1 — Copilot genera causas genéricas o repetitivas en el diagrama Ishikawa

**Síntoma:** La tabla del diagrama Ishikawa generada por Copilot contiene causas como "falta de capacitación", "falla de equipo" o "procedimiento inadecuado" que aplican a cualquier problema de manufactura sin ser específicas para el caso analizado.

**Causa:** El prompt inicial no proporcionó suficiente contexto técnico sobre el proceso específico (tipo de equipo, parámetros de proceso, condiciones de operación), lo que llevó a Copilot a generar respuestas genéricas basadas en patrones generales de manufactura.

**Solución:**
1. No inicies una nueva conversación; en la misma sesión, escribe un prompt de refinamiento que incluya detalles técnicos específicos del proceso:
   ```
   Las causas generadas son demasiado genéricas. Necesito causas específicas 
   para [descripción técnica del proceso: tipo de equipo, parámetros clave, 
   condiciones de operación]. Por ejemplo, en la categoría Máquina, considera 
   específicamente: [lista de componentes o sistemas relevantes del equipo]. 
   Por favor, regenera la tabla con ese nivel de especificidad técnica.
   ```
2. Si el problema persiste, proporciona un ejemplo de una causa específica para una categoría y pide a Copilot que siga ese nivel de detalle para las demás.
3. Como alternativa, puedes construir el Ishikawa de forma híbrida: usa Copilot para las categorías donde no tienes experiencia técnica y completa manualmente las categorías donde sí tienes conocimiento de planta.

---

### Problema 2 — La cadena de 5 Porqués de Copilot llega a una causa raíz superficial o da saltos lógicos entre niveles

**Síntoma:** La cadena de 5 Porqués termina en una causa como "el operador no siguió el procedimiento" (culpa individual) o presenta un salto entre el Por qué 3 y el Por qué 4 donde la conexión causal no es directa ni evidente.

**Causa:** Copilot puede tender a converger hacia causas de fácil atribución (error humano) o puede generar transiciones causales que suenan plausibles pero no están respaldadas por la lógica del caso específico. Esto ocurre especialmente cuando el prompt no solicita explícitamente causas sistémicas ni evidencias de soporte.

**Solución:**
1. Usa el siguiente prompt de corrección para redirigir el análisis:
   ```
   La cadena de 5 Porqués tiene dos problemas:
   
   Problema 1: La causa raíz final ("el operador no siguió el procedimiento") 
   es una causa individual, no sistémica. En metodología RCA rigurosa, una 
   causa raíz sistémica pregunta: ¿por qué el sistema permitió que ese error 
   ocurriera? Por favor, continúa la cadena un nivel más profundo para llegar 
   a la falla sistémica.
   
   Problema 2: La transición entre [Por qué N] y [Por qué N+1] no es directa. 
   [Por qué N+1] no es una causa directa de [Por qué N]. Por favor, propón 
   un paso intermedio o corrige la cadena para que cada nivel sea causa directa 
   del anterior.
   ```
2. Después de la corrección, verifica manualmente que puedas leer la cadena en sentido inverso (de la causa raíz hacia el síntoma) usando la frase "y por eso..." para confirmar la lógica.
3. Si después de dos refinamientos la cadena sigue siendo incorrecta, construye el Por qué 5 manualmente basándote en tu conocimiento del proceso y documenta en el Word que ese nivel fue completado por el analista, no por Copilot.

---

## 9. Limpieza del Entorno

Al finalizar la práctica, realiza las siguientes acciones para dejar el entorno ordenado y los archivos correctamente organizados:

1. **Guardar y sincronizar el documento final:**
   - Confirma que el archivo `RCA_Completo_[TuNombre]_[Fecha].docx` muestra el ícono de sincronización verde en OneDrive.
   - Si hay cambios pendientes de sincronización, espera a que se completen antes de cerrar Word.

2. **Organizar archivos en OneDrive:**
   - Mueve el archivo final a la carpeta del curso: `Curso M365 Copilot > Práctica 6 > Entregables`.
   - Si la carpeta no existe, créala con esa estructura.

3. **Cerrar conversaciones de Copilot Chat:**
   - En `copilot.microsoft.com`, no es necesario borrar el historial de conversaciones, pero si trabajas en un equipo compartido, cierra la sesión del navegador para proteger la privacidad de los datos simulados.

4. **Verificar que no se cargaron datos reales:**
   - Confirma que todos los datos utilizados en los prompts fueron los casos simulados de `casos_RCA_manufactura.docx` y no datos reales de tu planta.

5. **Compartir el entregable con el instructor:**
   - Si el instructor solicitó entrega, comparte el archivo desde OneDrive usando **Compartir > Personas específicas** con el correo del instructor, con permisos de **solo lectura**.

---

## 10. Resumen y Recursos Adicionales

### Resumen de lo Aprendido

En esta práctica construiste un proceso completo de Análisis de Causa Raíz (RCA) asistido por inteligencia artificial para tres casos reales de manufactura. Los aprendizajes clave son:

| Competencia desarrollada | Herramienta / Técnica utilizada |
|---|---|
| **Construcción de Ishikawa** | Prompts estructurados en Copilot Chat con contexto técnico específico |
| **Análisis de 5 Porqués** | Conversación iterativa con Copilot, validación de lógica causal |
| **Evaluación de contramedidas** | Prompts de validación de permanencia y detección de brechas |
| **Documentación ejecutiva** | Copilot en Word para estructurar reporte con formato de auditoría |
| **Pensamiento crítico sobre IA** | Evaluación de limitaciones y sesgos de Copilot en el análisis |

### Puntos Clave para Llevar a tu Planta

1. **Copilot amplifica, no reemplaza:** El valor de Copilot en el RCA está en acelerar la generación de hipótesis y estructurar el análisis, pero la validación con datos reales y el juicio experto del equipo son irreemplazables.

2. **La especificidad del prompt determina la calidad del análisis:** Un prompt genérico produce un Ishikawa genérico. Cuanto más contexto técnico proporciones (tipo de equipo, parámetros, condiciones), más útiles serán las causas generadas.

3. **La causa raíz debe ser sistémica:** Si el análisis de 5 Porqués termina en "error del operador", no has llegado a la causa raíz real. Pregunta siempre: ¿por qué el sistema permitió que ese error ocurriera?

4. **La permanencia de la contramedida es el verdadero indicador de éxito:** Una contramedida que requiere supervisión constante no es una solución permanente. Las mejores contramedidas modifican el sistema para que el error sea imposible o inmediatamente detectable.

5. **Documenta el proceso, no solo el resultado:** El reporte RCA en Word es valioso para auditorías, pero el aprendizaje organizacional ocurre cuando el proceso de análisis queda documentado y es reproducible por otros equipos.

### Recursos Adicionales

- 📘 [Microsoft Copilot — Guía de adopción en manufactura](https://adoption.microsoft.com/es-es/copilot/)
- 📘 [ASQ — Root Cause Analysis Resources](https://asq.org/quality-resources/root-cause-analysis)
- 📘 [AIAG — Core Tools para análisis de fallas (8D, FMEA)](https://www.aiag.org/quality/automotive-core-tools)
- 📘 [Industry Week — IA en manufactura moderna](https://www.industryweek.com/technology-and-iiot/article/21964440/artificial-intelligence-in-manufacturing)
- 📘 [Lean Enterprise Institute — 5 Whys Methodology](https://www.lean.org/lexicon-terms/5-whys/)

### Conexión con la Siguiente Práctica

Los reportes RCA generados en esta práctica serán utilizados como insumo en la **Práctica 7**, donde aprenderás a crear guías de restauración de proceso y planes de capacitación basados en los hallazgos del análisis de causa raíz. Asegúrate de que tu documento `RCA_Completo_[TuNombre]_[Fecha].docx` esté completo y sincronizado en OneDrive antes de la próxima sesión.

---
