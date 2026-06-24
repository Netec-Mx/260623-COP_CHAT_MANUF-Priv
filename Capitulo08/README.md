---LAB_START---
LAB_ID: 08-00-01
---MARKDOWN---
# Práctica 8 — Planes de Capacitación y Estrategias de Motivación con Copilot

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Crear |
| **Capítulo asociado** | Capítulo 8 — Liderazgo Efectivo en Manufactura |
| **Versión de la guía** | 1.0 |

---

## 2. Descripción General

En esta práctica aplicarás las competencias de liderazgo del Capítulo 8 para diseñar, con asistencia de Microsoft 365 Copilot, un plan integral de adopción de Copilot en planta. Partirás de perfiles detallados de cuatro roles operativos —operador de línea, técnico de mantenimiento, supervisor de turno y gerente de operaciones— para construir planes de capacitación diferenciados, mensajes de cambio adaptados a cada audiencia y una estrategia de gestión del cambio con fases de sensibilización, capacitación y consolidación. La práctica culmina con la generación automática de una presentación ejecutiva en PowerPoint lista para presentar a la dirección de planta.

---

## 3. Objetivos de Aprendizaje

Al finalizar esta práctica serás capaz de:

- [ ] **Diseñar** planes de capacitación personalizados para cuatro perfiles operativos de planta (operador, técnico, supervisor, gerente), utilizando Copilot en Word como asistente de estructuración y redacción.
- [ ] **Desarrollar** estrategias de motivación y gestión del cambio tecnológico que aborden las resistencias específicas del personal de planta ante la adopción de IA, apoyándote en Copilot Chat.
- [ ] **Adaptar** mensajes de comunicación del cambio al lenguaje, motivaciones y preocupaciones de cada perfil operativo, usando Copilot como redactor contextualizado.
- [ ] **Construir** un plan integral de despliegue de Copilot en planta con fases, métricas de adopción y estrategia de sostenibilidad, generado íntegramente con Copilot en Word y PowerPoint.

---

## 4. Prerrequisitos

### Conocimiento Previo

| Requisito | Descripción |
|---|---|
| Prácticas anteriores | Haber completado las Prácticas 1 a 7, o tener experiencia documentada en al menos 4 prácticas anteriores del curso |
| Gestión del cambio | Comprensión básica del modelo ADKAR (Awareness, Desire, Knowledge, Ability, Reinforcement) o equivalente |
| Liderazgo en manufactura | Familiaridad con los roles operativos de planta y sus responsabilidades diarias |
| Uso de Copilot | Capacidad para formular prompts estructurados en Copilot Chat y en las aplicaciones de Microsoft 365 |

### Acceso y Archivos Requeridos

| Recurso | Estado requerido |
|---|---|
| Cuenta Microsoft 365 con licencia Copilot activa | ✅ Verificado antes del inicio |
| Archivo `perfiles_roles_planta.docx` en OneDrive | ✅ Disponible (proporcionado por el instructor) |
| Microsoft Word (versión 2308 o posterior) con Copilot habilitado | ✅ Instalado |
| Microsoft PowerPoint (versión 2308 o posterior) con Copilot habilitado | ✅ Instalado |
| Copilot Chat en copilot.microsoft.com (modo Trabajo activo) | ✅ Sesión iniciada con cuenta corporativa |

> ⚠️ **Nota de privacidad:** Asegúrate de que Copilot Chat esté en **modo Trabajo (Work)** — identificado por el ícono de escudo corporativo en la interfaz — antes de cargar cualquier archivo o ingresar información de la práctica. No utilices datos reales de producción de tu empresa.

---

## 5. Entorno de Laboratorio

### Hardware Recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8va gen / AMD Ryzen 5 | Intel Core i7 10ma gen o superior |
| RAM | 8 GB | 16 GB |
| Resolución de pantalla | 1366 × 768 | 1920 × 1080 |
| Conexión a internet | 10 Mbps estable | Red corporativa cableada |
| Almacenamiento libre | 5 GB | 10 GB |

### Software y Configuración Inicial

| Aplicación | Versión mínima | Verificación |
|---|---|---|
| Microsoft Word | 2308 (Microsoft 365 Apps) | `Archivo → Cuenta → Acerca de Word` |
| Microsoft PowerPoint | 2308 (Microsoft 365 Apps) | `Archivo → Cuenta → Acerca de PowerPoint` |
| Microsoft Teams | 2.0 (New Teams) | Ícono de perfil → `Acerca de → Versión` |
| Copilot Chat (web) | copilot.microsoft.com | Verificar modo "Trabajo" activo |
| OneDrive for Business | Sincronización activa | Ícono de nube en barra de tareas |

### Configuración Previa al Inicio

Ejecuta los siguientes pasos de configuración **antes** de comenzar los ejercicios:

**Paso 1 — Verificar sincronización de OneDrive:**
```
1. Abre el Explorador de archivos
2. Navega a: OneDrive - [Tu organización] > Materiales_Curso_Copilot_Manufactura
3. Confirma que el archivo perfiles_roles_planta.docx aparece con ícono de nube verde (sincronizado)
```

**Paso 2 — Verificar modo Trabajo en Copilot Chat:**
```
1. Abre el navegador y ve a: https://copilot.microsoft.com
2. Inicia sesión con tu cuenta corporativa (@tuempresa.com)
3. Confirma que en la esquina superior derecha aparece tu foto de perfil corporativo
4. Verifica que el selector de modo muestre "Trabajo" (Work) y NO "Web"
5. Si aparece "Web", haz clic en el selector y cambia a "Trabajo"
```

**Paso 3 — Crear carpeta de entregables:**
```
1. En OneDrive, crea la carpeta: Practica_08_Capacitacion_Copilot
2. Esta carpeta almacenará todos los archivos generados en esta práctica
```

---

## 6. Instrucciones Paso a Paso

---

### Paso 1 — Revisión de Perfiles Operativos de Planta

**Objetivo:** Familiarizarte con los cuatro perfiles de roles de planta que servirán como base para todos los diseños de capacitación y comunicación de la práctica.

#### Instrucciones

1. Abre el archivo `perfiles_roles_planta.docx` desde OneDrive (doble clic desde el Explorador de archivos o desde OneDrive en el navegador).

2. Lee detenidamente los cuatro perfiles. Si el instructor no proporcionó el archivo o necesitas recrearlo, abre **Copilot Chat** en [copilot.microsoft.com](https://copilot.microsoft.com) y usa el siguiente prompt para generar los perfiles:

```
Actúa como experto en gestión del cambio organizacional en entornos de manufactura industrial.
Genera una tabla detallada con los perfiles de 4 roles operativos de planta para un programa
de adopción de Microsoft Copilot. Para cada perfil incluye:
- Nombre del rol
- Responsabilidades principales (3-4 puntos)
- Nivel de alfabetización digital (bajo/medio/alto)
- Motivaciones principales ante el cambio tecnológico (2-3 puntos)
- Resistencias o miedos típicos ante la IA (2-3 puntos)
- Canales de comunicación preferidos
- Disponibilidad para capacitación (horas/semana estimadas)

Los 4 roles son: (1) Operador de línea, (2) Técnico de mantenimiento,
(3) Supervisor de turno, (4) Gerente de operaciones.
Contexto: planta de manufactura discreta, industria automotriz, 500 empleados.
```

3. Copia la respuesta de Copilot Chat y pégala en un nuevo documento Word llamado `perfiles_roles_planta_generado.docx`. Guárdalo en la carpeta `Practica_08_Capacitacion_Copilot` de OneDrive.

4. Identifica y anota mentalmente (o en papel) los **2 principales miedos** de cada perfil ante la IA. Los usarás en el Paso 3.

#### Resultado Esperado

Tienes disponible una tabla con los 4 perfiles operativos que incluye nivel de alfabetización digital, motivaciones, resistencias y disponibilidad de tiempo. El documento está guardado en OneDrive.

#### Verificación

- [ ] El documento `perfiles_roles_planta.docx` (o `perfiles_roles_planta_generado.docx`) está abierto y visible.
- [ ] Puedes identificar el nivel de alfabetización digital de cada uno de los 4 roles.
- [ ] Puedes nombrar al menos 2 resistencias específicas del operador de línea ante la adopción de IA.

---

### Paso 2 — Diseño de Planes de Capacitación Diferenciados por Perfil

**Objetivo:** Usar Copilot en Word para generar planes de capacitación personalizados para cada uno de los cuatro perfiles operativos, con objetivos de aprendizaje, metodología, duración y materiales.

#### Instrucciones

1. Abre un **nuevo documento en blanco en Microsoft Word**. Nómbralo `plan_capacitacion_copilot_planta.docx` y guárdalo en la carpeta `Practica_08_Capacitacion_Copilot` de OneDrive **antes de comenzar** (esto activa la función de Copilot en Word).

2. Haz clic en el ícono de **Copilot** en la cinta de opciones de Word (pestaña `Inicio` → botón `Copilot`, o usa el atajo `Alt + I` en algunas versiones). Se abrirá el panel lateral de Copilot.

3. En el panel de Copilot en Word, ingresa el siguiente prompt para generar el plan del **Operador de Línea**:

```
Redacta un plan de capacitación detallado para el rol de Operador de Línea de una planta
automotriz de 500 empleados, enfocado en la adopción de Microsoft Copilot integrado en
Microsoft 365. El plan debe incluir:

1. Título del programa de capacitación
2. Perfil del participante (nivel digital: bajo, turno rotativo, resistencia al cambio alta)
3. Objetivo general de aprendizaje (1 objetivo)
4. Objetivos específicos (3 objetivos medibles, nivel Bloom: Recordar y Aplicar)
5. Contenido modular (3 módulos de 45 minutos cada uno, con tema y actividad práctica)
6. Metodología de enseñanza (adaptada a adultos con baja alfabetización digital)
7. Materiales requeridos (lista de recursos)
8. Métricas de evaluación de aprendizaje (2 indicadores)
9. Frecuencia y modalidad (presencial en planta, durante cambio de turno)

Usa un lenguaje claro, sin tecnicismos. Formato: secciones con encabezados H2.
```

4. Revisa el contenido generado. Si alguna sección no es adecuada para el contexto de manufactura, usa el botón **"Regenerar"** o agrega un prompt de refinamiento como:

```
Ajusta el Módulo 2 para incluir un ejercicio práctico donde el operador use Copilot Chat
para consultar el historial de paros de su línea en lenguaje natural, sin usar fórmulas.
```

5. Acepta el contenido generado haciendo clic en **"Conservar"** en el panel de Copilot.

6. Repite el proceso (pasos 3-5) para los tres perfiles restantes, usando estos prompts adaptados:

**Para Técnico de Mantenimiento:**
```
Redacta un plan de capacitación para el rol de Técnico de Mantenimiento de planta automotriz,
enfocado en adopción de Microsoft Copilot. El técnico tiene nivel digital medio, trabaja con
órdenes de trabajo en SAP y su principal resistencia es que "la IA cometerá errores en
diagnósticos críticos". El plan debe incluir los mismos 9 elementos del plan anterior,
pero con contenido adaptado a casos de uso de mantenimiento predictivo: análisis de
vibraciones, historial de fallas, generación de reportes técnicos con Copilot en Word
y consulta de manuales técnicos con Copilot Chat. Duración total: 3 módulos de 60 minutos.
```

**Para Supervisor de Turno:**
```
Redacta un plan de capacitación para el rol de Supervisor de Turno de planta automotriz,
enfocado en adopción de Microsoft Copilot como herramienta de liderazgo y toma de
decisiones. El supervisor tiene nivel digital medio-alto, gestiona equipos de 15-20 personas
y su resistencia es "perder autoridad si la IA toma las decisiones por mí". El plan debe
incluir los mismos 9 elementos, con contenido adaptado a: análisis de KPIs de turno con
Copilot en Excel, generación de briefings de turno con Copilot en Word, y comunicación
de resultados con Copilot en Teams. Duración total: 2 módulos de 90 minutos.
Nivel Bloom de los objetivos: Aplicar y Analizar.
```

**Para Gerente de Operaciones:**
```
Redacta un plan de capacitación ejecutiva para el rol de Gerente de Operaciones de planta
automotriz, enfocado en el uso estratégico de Microsoft Copilot para liderazgo transformacional.
El gerente tiene nivel digital alto, toma decisiones con impacto en toda la planta y su
resistencia es "no tengo tiempo para aprender otra herramienta". El plan debe incluir los
mismos 9 elementos, con contenido adaptado a: dashboards ejecutivos con Copilot en Excel,
presentaciones de resultados con Copilot en PowerPoint, y uso de Copilot para análisis
de causa raíz y planes de acción. Formato: sesión única de 2 horas tipo workshop ejecutivo.
Nivel Bloom: Analizar y Crear.
```

7. Asegúrate de que los cuatro planes estén en el mismo documento `plan_capacitacion_copilot_planta.docx`, separados por saltos de página. Usa `Ctrl + Enter` para insertar saltos de página entre cada plan.

8. Guarda el documento con `Ctrl + S`.

#### Resultado Esperado

El documento `plan_capacitacion_copilot_planta.docx` contiene cuatro planes de capacitación completos, uno por perfil, con diferencias claras en nivel de lenguaje, duración, metodología y casos de uso de Copilot. Cada plan tiene al menos 9 secciones estructuradas con encabezados.

#### Verificación

- [ ] El documento contiene 4 planes diferenciados (uno por perfil).
- [ ] Cada plan incluye objetivos de aprendizaje con nivel Bloom explícito.
- [ ] El lenguaje del plan del Operador es notablemente más simple que el del Gerente.
- [ ] Cada plan menciona al menos un caso de uso específico de Copilot en manufactura.
- [ ] El documento está guardado en OneDrive (`Practica_08_Capacitacion_Copilot`).

---

### Paso 3 — Desarrollo de Mensajes de Cambio Adaptados por Perfil

**Objetivo:** Usar Copilot en Word para redactar mensajes de comunicación del cambio tecnológico adaptados al lenguaje, motivaciones y preocupaciones de cada perfil operativo, aplicando los principios de comunicación adaptativa de la Lección 8.3.

#### Instrucciones

1. Abre un **nuevo documento en Word** llamado `mensajes_cambio_tecnologico.docx` y guárdalo en la carpeta `Practica_08_Capacitacion_Copilot` de OneDrive.

2. En el panel de Copilot en Word, genera el mensaje para el **Operador de Línea**:

```
Redacta un mensaje de comunicación interna dirigido a operadores de línea de una planta
automotriz para anunciar la implementación de Microsoft Copilot en sus operaciones diarias.

Contexto del destinatario:
- Nivel educativo: secundaria/bachillerato técnico
- Miedo principal: "me van a reemplazar con la IA"
- Motivación: estabilidad laboral, reconocimiento del equipo, trabajo más fácil
- Canal: cartelera de planta + reunión de 5 minutos al inicio del turno
- Tono: cercano, directo, sin tecnicismos

El mensaje debe:
1. Tener un titular impactante y positivo (máx. 10 palabras)
2. Responder directamente al miedo de reemplazo (2-3 oraciones)
3. Explicar en qué cambiará su trabajo diario con Copilot (3 ejemplos concretos)
4. Incluir un llamado a la acción claro (qué hacer esta semana)
5. Cerrar con un mensaje motivacional alineado a la cultura de equipo
Extensión máxima: 200 palabras.
```

3. Revisa el mensaje. Verifica que el lenguaje sea accesible (sin términos como "inteligencia artificial generativa", "modelo de lenguaje" o "API"). Si Copilot usó tecnicismos, usa este prompt de refinamiento:

```
Reescribe el mensaje eliminando todos los tecnicismos de tecnología. Reemplaza cualquier
término técnico con una analogía cotidiana que un operador de línea pueda entender
fácilmente. Mantén el mismo tono cercano y la misma estructura.
```

4. Genera el mensaje para el **Técnico de Mantenimiento**:

```
Redacta un mensaje de comunicación interna dirigido a técnicos de mantenimiento de planta
automotriz para anunciar la implementación de Microsoft Copilot.

Contexto del destinatario:
- Perfil: técnico especializado, 5-15 años de experiencia, conocimiento profundo de equipos
- Miedo principal: "Copilot dará diagnósticos incorrectos y causará daños en los equipos"
- Motivación: ser reconocido como experto, resolver problemas más rápido, reducir guardias nocturnas
- Canal: correo electrónico técnico + reunión de área
- Tono: técnico pero accesible, respeta su expertise, posiciona Copilot como asistente (no reemplazo)

El mensaje debe:
1. Reconocer explícitamente el valor del expertise del técnico
2. Aclarar que Copilot es un asistente que potencia (no reemplaza) su juicio técnico
3. Dar 2 ejemplos concretos de cómo Copilot ayudará en mantenimiento predictivo
4. Invitar a una demostración técnica voluntaria
Extensión máxima: 250 palabras. Formato: correo electrónico con asunto, saludo y firma.
```

5. Genera el mensaje para el **Supervisor de Turno**:

```
Redacta un mensaje dirigido a supervisores de turno de planta automotriz sobre la
implementación de Microsoft Copilot como herramienta de liderazgo.

Contexto:
- Miedo principal: "perderé autoridad si la IA toma las decisiones"
- Motivación: reconocimiento de su liderazgo, mejores resultados de turno, menos trabajo administrativo
- Canal: reunión de supervisores + Teams
- Tono: profesional, estratégico, posiciona al supervisor como líder del cambio (no receptor del cambio)

El mensaje debe:
1. Posicionar al supervisor como agente clave de la transformación digital en planta
2. Explicar cómo Copilot libera tiempo administrativo para que el supervisor lidere más
3. Describir 2 escenarios donde Copilot fortalece (no reemplaza) la autoridad del supervisor
4. Incluir una invitación a ser "embajador digital" del equipo
Extensión: 300 palabras máximo.
```

6. Genera el mensaje para el **Gerente de Operaciones**:

```
Redacta un mensaje ejecutivo dirigido al Gerente de Operaciones de una planta automotriz
sobre la implementación estratégica de Microsoft Copilot en la planta.

Contexto:
- Perfil: ejecutivo con visión de negocio, orientado a resultados, tiempo limitado
- Miedo: "no tengo tiempo para aprender otra herramienta" / "¿esto realmente impactará los KPIs?"
- Motivación: reducción de costos, mejora de OEE, ventaja competitiva, liderazgo de la transformación
- Canal: reporte ejecutivo de 1 página + presentación de 5 minutos en comité directivo
- Tono: ejecutivo, orientado a ROI, datos y resultados, lenguaje de negocio

El mensaje debe:
1. Abrir con un dato de impacto (benchmark de industria sobre adopción de IA en manufactura)
2. Conectar Copilot directamente con los KPIs de planta: OEE, MTTR, tasa de defectos
3. Presentar el plan de adopción como una inversión con retorno medible (3-6 meses)
4. Solicitar aprobación de recursos y patrocinio ejecutivo del programa
Formato: memo ejecutivo con encabezado formal. Extensión: 350 palabras máximo.
```

7. Asegúrate de que los cuatro mensajes estén en el documento `mensajes_cambio_tecnologico.docx`, separados por saltos de página. Guarda con `Ctrl + S`.

#### Resultado Esperado

El documento `mensajes_cambio_tecnologico.docx` contiene cuatro mensajes de comunicación del cambio, cada uno con tono, formato y lenguaje claramente diferenciados según el perfil del destinatario. Los mensajes abordan directamente los miedos específicos de cada rol y ofrecen un llamado a la acción concreto.

#### Verificación

- [ ] El mensaje del Operador está en lenguaje simple, sin tecnicismos, con extensión ≤ 200 palabras.
- [ ] El mensaje del Técnico reconoce explícitamente su expertise y posiciona Copilot como asistente.
- [ ] El mensaje del Supervisor lo posiciona como agente de cambio, no como receptor.
- [ ] El mensaje del Gerente usa lenguaje de negocio con mención de KPIs (OEE, MTTR, defectos).
- [ ] El documento está guardado en OneDrive.

---

### Paso 4 — Construcción de la Estrategia de Gestión del Cambio

**Objetivo:** Usar Copilot Chat para construir una estrategia integral de gestión del cambio tecnológico con tres fases (sensibilización, capacitación y consolidación), métricas de adopción y plan de sostenibilidad, aplicando el marco de liderazgo del Capítulo 8.

#### Instrucciones

1. Abre **Copilot Chat** en [copilot.microsoft.com](https://copilot.microsoft.com) (modo Trabajo activo). Abre también el documento `plan_capacitacion_copilot_planta.docx` en Word para tenerlo como referencia.

2. En Copilot Chat, ingresa el siguiente prompt para generar la estrategia de gestión del cambio:

```
Actúa como consultor senior en gestión del cambio organizacional con especialización en
transformación digital en manufactura industrial.

Diseña una estrategia completa de gestión del cambio para la implementación de Microsoft
Copilot en una planta automotriz de 500 empleados. La estrategia debe seguir el modelo
ADKAR (Awareness, Desire, Knowledge, Ability, Reinforcement) y estructurarse en 3 fases:

FASE 1 — SENSIBILIZACIÓN (Semanas 1-4):
- Actividades clave por fase
- Responsables (por rol: gerente, supervisor, técnico de TI, RH)
- Canales de comunicación
- Entregables de la fase

FASE 2 — CAPACITACIÓN (Semanas 5-12):
- Programa de formación diferenciado por perfil (referencia: 4 planes de capacitación)
- Metodología de capacitación en planta (sin interrumpir producción)
- Recursos necesarios (instructores, materiales, tiempo)
- Entregables de la fase

FASE 3 — CONSOLIDACIÓN (Semanas 13-24):
- Mecanismos de refuerzo y sostenibilidad
- Programa de embajadores digitales en planta
- Comunidad de práctica interna
- Entregables de la fase

Para cada fase incluye:
- Duración y hitos clave
- Riesgos principales y mitigaciones
- 3 métricas de adopción medibles (con valores objetivo)

Al final, incluye una sección de "Indicadores de Éxito del Programa" con 5 KPIs de adopción
de Copilot medibles a 6 meses (ej: % de usuarios activos semanales, reducción de tiempo
en generación de reportes, etc.).

Formato: estructura con encabezados claros, tablas donde sea útil.
```

3. Copia la respuesta completa de Copilot Chat. Abre un **nuevo documento Word** llamado `estrategia_gestion_cambio_copilot.docx`, pega el contenido y guárdalo en `Practica_08_Capacitacion_Copilot` en OneDrive.

4. En el panel de **Copilot en Word** (dentro del documento recién creado), usa el siguiente prompt para mejorar el formato y agregar un resumen ejecutivo:

```
Agrega al inicio de este documento un resumen ejecutivo de máximo 150 palabras que sintetice
la estrategia de gestión del cambio, dirigido a la dirección general de la planta. El resumen
debe mencionar: duración total del programa (6 meses), número de empleados impactados (500),
las 3 fases del plan y el beneficio esperado en términos de adopción de Copilot y mejora
de indicadores operativos. Tono: ejecutivo y orientado a resultados.
```

5. Acepta el contenido generado y guarda el documento con `Ctrl + S`.

6. **Actividad de reflexión crítica (5 minutos):** Revisa las métricas de adopción propuestas por Copilot. Identifica si alguna métrica no es realista para tu contexto de planta. En el documento, agrega una nota manual con el comentario de Word (`Revisar → Nuevo comentario`) indicando qué métrica ajustarías y por qué.

> 💡 **Recuerda:** Las respuestas de Copilot son generativas y referenciales. Siempre evalúa críticamente el contenido antes de presentarlo a la dirección. Tu juicio como líder de planta es el filtro más importante.

#### Resultado Esperado

El documento `estrategia_gestion_cambio_copilot.docx` contiene una estrategia completa de 3 fases con actividades, responsables, métricas y un resumen ejecutivo. Incluye al menos 5 KPIs de adopción medibles y al menos 1 comentario de revisión crítica del participante.

#### Verificación

- [ ] El documento tiene un resumen ejecutivo al inicio (≤ 150 palabras).
- [ ] Las 3 fases (Sensibilización, Capacitación, Consolidación) están claramente diferenciadas con fechas.
- [ ] Cada fase tiene al menos 3 métricas de adopción con valores objetivo.
- [ ] El documento contiene al menos 1 comentario de revisión crítica del participante.
- [ ] El archivo está guardado en OneDrive.

---

### Paso 5 — Generación de la Presentación Ejecutiva en PowerPoint con Copilot

**Objetivo:** Usar Copilot en PowerPoint para generar automáticamente una presentación ejecutiva del Plan de Despliegue de Copilot en Planta, lista para presentar a la dirección, integrando los documentos generados en los pasos anteriores.

#### Instrucciones

1. Abre **Microsoft PowerPoint**. Crea un nuevo archivo en blanco y guárdalo como `presentacion_despliegue_copilot_planta.pptx` en la carpeta `Practica_08_Capacitacion_Copilot` de OneDrive.

2. Haz clic en el ícono de **Copilot** en la cinta de opciones de PowerPoint (pestaña `Inicio` o `Copilot` según tu versión). Se abrirá el panel lateral de Copilot.

3. En el panel de Copilot en PowerPoint, usa el siguiente prompt para generar la presentación completa:

```
Crea una presentación ejecutiva profesional con el siguiente contenido. Usa diseño
corporativo limpio con paleta de colores azul y gris. Incluye exactamente las siguientes
diapositivas:

Diapositiva 1 — PORTADA:
Título: "Plan de Despliegue de Microsoft Copilot en Planta"
Subtítulo: "Estrategia de Capacitación, Gestión del Cambio y Adopción Sostenible"
Pie: "[Nombre de la Planta] | [Mes Año]"

Diapositiva 2 — AGENDA:
Lista las 6 secciones de la presentación

Diapositiva 3 — CONTEXTO Y JUSTIFICACIÓN:
Por qué adoptar Copilot en manufactura ahora. 3 datos de impacto de la industria.
Un gráfico de barras comparativo: plantas con IA vs. sin IA en OEE y tiempo de respuesta.

Diapositiva 4 — PERFILES Y NECESIDADES DE CAPACITACIÓN:
Tabla de 4 filas (Operador, Técnico, Supervisor, Gerente) con columnas:
Perfil | Nivel Digital | Resistencia Principal | Enfoque de Capacitación | Duración

Diapositiva 5 — PLAN DE CAPACITACIÓN DIFERENCIADO:
Resumen visual de los 4 planes de capacitación. Íconos por perfil.
Métricas de aprendizaje esperadas por rol.

Diapositiva 6 — ESTRATEGIA DE GESTIÓN DEL CAMBIO (MODELO ADKAR):
Diagrama de las 3 fases: Sensibilización (sem 1-4), Capacitación (sem 5-12),
Consolidación (sem 13-24). Timeline visual horizontal.

Diapositiva 7 — MENSAJES CLAVE POR AUDIENCIA:
4 cuadrantes (uno por perfil) con el mensaje central de cambio adaptado.
Resalta el beneficio clave para cada rol.

Diapositiva 8 — MÉTRICAS DE ADOPCIÓN Y KPIs:
Tabla con 5 KPIs del programa: nombre, línea base, objetivo a 6 meses, responsable.
Incluye: % usuarios activos, tiempo en reportes, satisfacción del usuario, adopción por turno.

Diapositiva 9 — INVERSIÓN Y ROI ESPERADO:
Tabla de recursos requeridos (horas de capacitación, materiales, coordinador).
Beneficio esperado en reducción de tiempo operativo y mejora de OEE.

Diapositiva 10 — PRÓXIMOS PASOS Y SOLICITUD DE APROBACIÓN:
3 acciones inmediatas (próximas 2 semanas).
Solicitud de aprobación del programa a la dirección.
Información de contacto del líder del proyecto.

Usa viñetas concisas, máximo 5 puntos por diapositiva. Incluye notas del orador
en cada diapositiva con 2-3 oraciones de contexto para el presentador.
```

4. Espera a que Copilot genere las diapositivas (puede tomar 30-60 segundos). Revisa el resultado.

5. Si alguna diapositiva necesita ajuste, usa prompts específicos en el panel de Copilot de PowerPoint:

```
// Para mejorar una diapositiva específica:
Mejora la diapositiva 6 agregando íconos visuales para cada fase del modelo ADKAR
y resalta con color diferente los hitos clave de cada fase.

// Para agregar más impacto visual:
Agrega a la diapositiva 3 un dato de benchmark: "Las plantas que adoptan IA en manufactura
reportan una reducción del 20-30% en tiempo de paros no planificados según Deloitte 2024".

// Para ajustar el tono ejecutivo:
Revisa todas las diapositivas y asegúrate de que el lenguaje sea ejecutivo, orientado
a resultados de negocio, sin tecnicismos de TI. Máximo 5 palabras por viñeta.
```

6. Aplica el **tema corporativo** de tu organización si está disponible: `Diseño → Temas → [Tema corporativo]`. Si no hay tema corporativo, selecciona el tema **"Ion"** o **"Faceta"** de PowerPoint para una apariencia profesional.

7. Revisa las **notas del orador** en cada diapositiva (`Vista → Vista Normal → panel de notas`). Complementa manualmente las notas de la diapositiva 10 (Próximos Pasos) con el nombre real del responsable del proyecto y las fechas concretas de tu contexto.

8. Guarda la presentación con `Ctrl + S`.

#### Resultado Esperado

El archivo `presentacion_despliegue_copilot_planta.pptx` contiene 10 diapositivas con diseño profesional, contenido ejecutivo diferenciado por audiencia, métricas de adopción, timeline visual de las 3 fases y notas del orador en cada diapositiva. La presentación está lista para ser usada en un comité directivo.

#### Verificación

- [ ] La presentación tiene exactamente 10 diapositivas (o más, si Copilot agregó adicionales con contenido relevante).
- [ ] La diapositiva 4 contiene la tabla de 4 perfiles con sus columnas completas.
- [ ] La diapositiva 6 muestra el timeline de las 3 fases de gestión del cambio.
- [ ] La diapositiva 8 contiene al menos 5 KPIs con línea base y objetivo.
- [ ] Todas las diapositivas tienen notas del orador.
- [ ] El archivo está guardado en OneDrive.

---

### Paso 6 — Compartir y Colaborar en Teams

**Objetivo:** Publicar los entregables de la práctica en un canal de Microsoft Teams para revisión del equipo, usando Copilot en Teams para generar un resumen del plan de despliegue.

#### Instrucciones

1. Abre **Microsoft Teams** (versión New Teams 2.0).

2. Navega al canal de tu equipo de curso: `Equipos → [Nombre del equipo del curso] → Canal: Práctica 8`.

3. Haz clic en **"+"** para adjuntar archivos y sube los siguientes entregables desde OneDrive:
   - `plan_capacitacion_copilot_planta.docx`
   - `mensajes_cambio_tecnologico.docx`
   - `estrategia_gestion_cambio_copilot.docx`
   - `presentacion_despliegue_copilot_planta.pptx`

4. En el cuadro de mensaje del canal, haz clic en el ícono de **Copilot** (o usa `@Copilot` en el mensaje) y escribe:

```
Resume en 5 puntos clave el plan de despliegue de Copilot en planta que compartí en
este canal. Incluye: objetivo del programa, perfiles capacitados, duración total,
métricas principales y próximo paso de acción. Formato: lista numerada, lenguaje ejecutivo.
```

5. Copia el resumen generado por Copilot en Teams y agrégalo como mensaje de texto en el canal, precedido por el encabezado:

```
📋 **Resumen Ejecutivo — Plan de Despliegue Copilot en Planta**
[Pega aquí el resumen generado por Copilot]
```

6. Agrega una reacción 👍 al mensaje de al menos un compañero de equipo que haya compartido sus entregables.

#### Resultado Esperado

Los 4 entregables de la práctica están publicados en el canal de Teams. El canal muestra un resumen ejecutivo del plan generado con Copilot en Teams, visible para todos los miembros del equipo.

#### Verificación

- [ ] Los 4 archivos aparecen en la pestaña `Archivos` del canal de Teams.
- [ ] El resumen ejecutivo está publicado como mensaje en el canal.
- [ ] El resumen menciona los 4 perfiles, la duración del programa y al menos 2 métricas.

---

## 7. Validación y Pruebas

### Lista de Verificación Final de Entregables

Completa esta lista antes de declarar la práctica terminada:

| # | Entregable | Archivo | Criterio de calidad | ✅ |
|---|---|---|---|---|
| 1 | Planes de capacitación | `plan_capacitacion_copilot_planta.docx` | 4 planes diferenciados, 9 secciones c/u, lenguaje adaptado por perfil | ☐ |
| 2 | Mensajes de cambio | `mensajes_cambio_tecnologico.docx` | 4 mensajes, tono diferenciado, miedos abordados directamente | ☐ |
| 3 | Estrategia de gestión del cambio | `estrategia_gestion_cambio_copilot.docx` | 3 fases ADKAR, 5 KPIs, resumen ejecutivo, comentario crítico del participante | ☐ |
| 4 | Presentación ejecutiva | `presentacion_despliegue_copilot_planta.pptx` | 10 diapositivas, diseño profesional, notas del orador | ☐ |
| 5 | Publicación en Teams | Canal Práctica 8 | 4 archivos subidos, resumen publicado | ☐ |

### Prueba de Calidad de Prompts

Realiza esta prueba rápida para verificar tu comprensión de la ingeniería de prompts aplicada en la práctica:

1. Abre Copilot Chat y escribe el siguiente prompt de prueba:

```
¿Cuál es la diferencia entre un mensaje de cambio tecnológico dirigido a un operador
de línea con baja alfabetización digital versus uno dirigido a un gerente de operaciones?
Dame 3 diferencias específicas en: tono, vocabulario y estructura del mensaje.
```

2. Verifica que la respuesta de Copilot identifique diferencias claras y coherentes con los mensajes que generaste en el Paso 3. Si hay inconsistencias, anótalas como aprendizaje.

---

## 8. Solución de Problemas

### Problema 1 — Copilot en Word no genera contenido estructurado con encabezados

**Síntoma:** Al usar el panel de Copilot en Word, el contenido se genera como texto plano sin encabezados H2/H3, dificultando la organización del documento de planes de capacitación.

**Causa:** El prompt no especificó explícitamente el formato de salida, o la versión de Word no aplica automáticamente los estilos de encabezado al contenido generado por Copilot.

**Solución:**
1. Agrega al final de tu prompt la instrucción: `"Usa el formato de estilos de Word: Título 1 para secciones principales, Título 2 para subsecciones, texto normal para el contenido."` Sin embargo, si Copilot sigue generando texto plano, aplica los estilos manualmente:
   - Selecciona el texto del título de sección → `Inicio → Estilos → Título 2`
2. Alternativa: genera el contenido en Copilot Chat (copilot.microsoft.com), cópialo con formato Markdown y pégalo en Word usando `Pegado especial → Mantener formato de origen`. Word convertirá los encabezados Markdown (`##`) en estilos de título automáticamente.
3. Si el problema persiste, verifica que la versión de Word sea 2308 o posterior: `Archivo → Cuenta → Acerca de Word`. Si es anterior, actualiza desde `Archivo → Cuenta → Opciones de actualización → Actualizar ahora`.

---

### Problema 2 — Copilot en PowerPoint genera diapositivas con texto excesivo o sin diseño visual

**Síntoma:** La presentación generada por Copilot en PowerPoint contiene diapositivas con párrafos completos en lugar de viñetas concisas, o el diseño visual es genérico y no tiene el aspecto ejecutivo esperado.

**Causa:** El prompt no fue suficientemente específico en las restricciones de formato (máximo de palabras por viñeta, tipo de gráficos), o la versión de Copilot en PowerPoint disponible tiene capacidades limitadas de diseño automático.

**Solución:**
1. **Para reducir el texto:** Selecciona la diapositiva problemática en el panel de Copilot de PowerPoint y usa el prompt: `"Condensa el contenido de esta diapositiva a máximo 5 viñetas de no más de 8 palabras cada una. Elimina todo el texto explicativo."` Repite para cada diapositiva con exceso de texto.
2. **Para mejorar el diseño visual:** Ve a `Diseño → Ideas de diseño` (Design Ideas) — esta función de PowerPoint (no Copilot) sugerirá layouts visuales profesionales para el contenido actual. Selecciona el diseño más apropiado para cada diapositiva.
3. **Alternativa completa:** Si el resultado de Copilot en PowerPoint no es satisfactorio, genera el contenido de cada diapositiva en Copilot Chat como texto estructurado, luego crea las diapositivas manualmente usando plantillas de PowerPoint de Microsoft (disponibles en `Archivo → Nuevo → Buscar plantillas en línea: "presentación ejecutiva"`).

---

## 9. Limpieza del Entorno

Al finalizar la práctica, realiza los siguientes pasos de limpieza y cierre:

1. **Guardar todos los archivos finales:**
   ```
   Verifica que los 4 entregables estén guardados en OneDrive:
   OneDrive > Practica_08_Capacitacion_Copilot > [4 archivos]
   ```

2. **Cerrar sesiones de Copilot Chat:**
   ```
   En copilot.microsoft.com → haz clic en "Nueva conversación" para limpiar
   el historial de la sesión de práctica. No es necesario cerrar sesión de M365.
   ```

3. **Verificar sincronización de OneDrive:**
   ```
   Clic derecho en el ícono de OneDrive en la barra de tareas → "Ver sincronización"
   Confirma que todos los archivos muestran ícono de nube verde (sincronizado).
   ```

4. **Compartir enlace de la carpeta con el instructor (si se solicita):**
   ```
   En OneDrive (web) → carpeta Practica_08_Capacitacion_Copilot →
   clic derecho → "Compartir" → "Copiar vínculo" → enviar por Teams al instructor.
   ```

5. **Opcional — Exportar presentación a PDF para archivo:**
   ```
   En PowerPoint: Archivo → Exportar → Crear PDF/XPS → guardar como
   presentacion_despliegue_copilot_planta.pdf en la misma carpeta de OneDrive.
   ```

> ℹ️ **Nota:** No elimines los archivos de esta práctica. Pueden ser utilizados como plantillas de referencia en tu trabajo real de planta o como portafolio de competencias del curso.

---

## 10. Resumen

### Lo que Aprendiste en Esta Práctica

En esta práctica de 90 minutos aplicaste las competencias de liderazgo del Capítulo 8 para construir, con asistencia de Microsoft 365 Copilot, un plan integral y ejecutable de adopción de Copilot en planta. Los logros clave de esta sesión fueron:

| Competencia desarrollada | Herramienta utilizada | Entregable generado |
|---|---|---|
| Diseño de capacitación diferenciada por perfil | Copilot en Word | `plan_capacitacion_copilot_planta.docx` |
| Comunicación adaptativa del cambio tecnológico | Copilot en Word | `mensajes_cambio_tecnologico.docx` |
| Estrategia de gestión del cambio (modelo ADKAR) | Copilot Chat + Copilot en Word | `estrategia_gestion_cambio_copilot.docx` |
| Presentación ejecutiva de plan de despliegue | Copilot en PowerPoint | `presentacion_despliegue_copilot_planta.pptx` |
| Colaboración y síntesis en equipo | Copilot en Teams | Publicación en canal del curso |

### Conexión con el Capítulo 8

Esta práctica materializó los dos pilares del Capítulo 8:

- **Lección 8.2 (Gestión del cambio tecnológico):** Aplicaste el modelo ADKAR para diseñar una estrategia de 3 fases que reduce la resistencia y guía a los equipos de planta hacia la adopción efectiva de Copilot.
- **Lección 8.3 (Comunicación adaptativa):** Demostraste la capacidad de diferenciar mensajes, tono y formato según el perfil del interlocutor operativo — desde el operador de línea hasta el gerente de operaciones.

Ambas competencias son el **multiplicador de valor** de todo lo aprendido en los capítulos anteriores: los análisis de calidad, los modelos predictivos de mantenimiento, los dashboards de OEE y los reportes de causa raíz solo generan impacto sostenible cuando un líder sabe cómo comunicarlos, contextualizarlos y motivar a su equipo a actuar sobre ellos.

### Reflexión Final

> *"Copilot puede generar análisis brillantes. Pero eres tú, como líder, quien decide cómo presentarlos, a quién comunicarlos y cómo motivar a tu equipo a actuar. La IA amplifica tu liderazgo; no lo reemplaza."*

### Recursos Adicionales

| Recurso | Descripción | Enlace |
|---|---|---|
| Prosci — Modelo ADKAR | Marco de referencia para gestión del cambio organizacional | [prosci.com/methodology/adkar](https://www.prosci.com/methodology/adkar) |
| Microsoft Adoption Hub | Recursos oficiales para adopción de Copilot en organizaciones | [adoption.microsoft.com/es-es/copilot](https://adoption.microsoft.com/es-es/copilot/) |
| Kotter — Leading Change | Artículo seminal sobre liderazgo del cambio (HBR) | [hbr.org/1995/05/leading-change](https://hbr.org/1995/05/leading-change-why-transformation-efforts-fail) |
| Microsoft Copilot Scenario Library | Biblioteca de escenarios de uso de Copilot por industria | [adoption.microsoft.com/copilot-scenario-library](https://adoption.microsoft.com/en-us/copilot-scenario-library/) |
| Deloitte — Leadership in Digital Manufacturing | Investigación sobre liderazgo en la fábrica digital | [deloitte.com/insights/industry-4-0](https://www2.deloitte.com/us/en/insights/focus/industry-4-0/leadership-in-digital-manufacturing.html) |

---

*Fin del Laboratorio 08-00-01 — Práctica 8: Planes de Capacitación y Estrategias de Motivación con Copilot*

---
LAB_END---
