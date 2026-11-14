# Práctica 8. Uso avanzado de NotebookLM alimentado con el histórico de normativas, manuales y documentos generados por la DPCI para crear un repositorio inteligente de consulta rápida, síntesis profunda y redacción de materiales de capacitación

**Duración de la práctica:** 30 min

## Descripción
Los participantes utilizarán exclusivamente el ecosistema de Google (**Google Gemini** y **Google NotebookLM**) para construir una base de conocimiento institucional inteligente de la DPCI. A partir de normativas, manuales técnicos y lineamientos administrativos 100% autogenerados en Gemini, los asistentes alimentarán un cuaderno en **NotebookLM** para ejecutar consultas con citas verificables (cero alucinaciones), síntesis profunda entre múltiples fuentes, generación de guías de estudio y redacción de materiales de capacitación interna.

---

## Sección 1: Demostración del Instructor (3 Pasos)

1. **Autogeneración de normativa y manual operativo base en Google Gemini:**
   * El instructor abre **Google Gemini** y envía el siguiente prompt para crear dos documentos institucionales ficticios que servirán como fuentes para NotebookLM:
     ```text
     Actúa como un Especialista en Normatividad y Procesos de la DPCI.
     
     Genera dos textos institucionales breves (de 200 palabras cada uno) claramente separados:
     - FUENTE 1: "Resolución Interna 015 de Gobernanza de Datos DPCI" (establece reglas de clasificación de información pública, reservada y confidencial, y plazos de retención de 5 años).
     - FUENTE 2: "Manual Operativo de Radicación y Archivo Digital" (define el flujo de 3 pasos para recepción de expedientes, tiempos máximos de respuesta de 10 días hábiles y uso obligatorio de firma electrónica).
     ```

2. **Creación del cuaderno inteligente y carga de fuentes en NotebookLM:**
   * El instructor abre **Google NotebookLM** (`notebooklm.google.com`), hace clic en **Crear nuevo cuaderno** y lo nombra `Repositorio_Normativo_DPCI`.
   * Selecciona **Agregar fuente > Texto copiado**, pega la **Fuente 1** (titulándola `Resolucion_015_Gobernanza`) y repite el proceso para agregar la **Fuente 2** (titulándola `Manual_Operativo_Archivo`).

3. **Consulta cruzada con citas verificables y generación de guía rápida en NotebookLM:**
   * En el panel de chat de **NotebookLM**, el instructor formula una pregunta que exige cruzar ambos documentos y verifica las citas numeradas interactivas:
     ```text
     Con base estricta en las dos fuentes cargadas, ¿qué plazo de retención documental aplica a un expediente recibido por radicación digital y cuál es el tiempo máximo de respuesta permitido? Indica exactamente de qué fuente proviene cada dato.
     ```
   * Luego, en el panel derecho (**Studio**), hace clic en **Guía de estudio** (o **Documento de resumen**) para mostrar cómo NotebookLM sintetiza automáticamente preguntas frecuentes y conceptos clave.

---

## Sección 2: Práctica Guiada del Participante (30 min)

1. **Autogeneración del histórico documental institucional (3 Fuentes) en Google Gemini:**
   * Abre **Google Gemini** y envía el siguiente prompt para generar el paquete completo de normativas, manuales y reportes históricos de la DPCI:
     ```text
     Actúa como un Arquitecto de Procesos y Control Interno de la DPCI.
     
     Genera 3 documentos institucionales detallados (de unas 300 palabras cada uno) claramente separados por títulos, con cifras, plazos y reglas específicas:
     
     DOCUMENTO 1: "Política Integral de Seguridad de la Información y Uso de IA en la DPCI (Acuerdo 088)"
     - Prohíbe cargar datos personales (PII) o contratos reservados en modelos públicos sin anonimización previa.
     - Exige doble validación humana para informes financieros superiores a $50.000 USD.
     - Establece auditorías trimestrales de cumplimiento lideradas por la Oficina de Control Interno.
     
     DOCUMENTO 2: "Manual Técnico de Contratación y Supervisión de Proyectos de Infraestructura (MT-2026)"
     - Define 4 etapas obligatorias: Planeación, Selección, Ejecución y Liquidación.
     - Exige que todo contrato superior a $100.000 USD cuente con interventoría externa y póliza de cumplimiento del 20%.
     - Establece un límite máximo de 15 días hábiles para aprobar actas de avance de obra.
     
     DOCUMENTO 3: "Informe Histórico de Lecciones Aprendidas y Hallazgos de Auditoría (2024-2025)"
     - Reporta que el 35% de los retrasos en proyectos se debió a demoras mayores a 20 días en la revisión de actas de avance.
     - Señala 2 incidentes de fuga de datos menores por uso de herramientas de IA sin protocolos de enmascaramiento.
     - Recomienda capacitar al 100% de los supervisores en herramientas de análisis documental y control de riesgos.
     ```

2. **Construcción del Repositorio Inteligente en Google NotebookLM:**
   * Abre **Google NotebookLM** (`notebooklm.google.com`) en una nueva pestaña e inicia sesión con tu cuenta de Google.
   * Haz clic en **Crear nuevo cuaderno** y asígnale el nombre: `Base_Conocimiento_DPCI_2026`.
   * Carga las 3 fuentes generadas en el Paso 1 una por una haciendo clic en **Agregar fuente > Texto copiado**:
     * Fuente 1: Titúlala `Acuerdo_088_Seguridad_IA` y pega el **Documento 1**.
     * Fuente 2: Titúlala `Manual_Contratacion_MT2026` y pega el **Documento 2**.
     * Fuente 3: Titúlala `Informe_Lecciones_Aprendidas` y pega el **Documento 3**.
   * Verifica que en el panel izquierdo aparezcan las 3 fuentes seleccionadas con su casilla marcada.

3. **Síntesis profunda y cruce de brechas normativas vs. realidad operativa en NotebookLM:**
   * En el cuadro de chat central de **NotebookLM**, envía el siguiente prompt para obligar al sistema a cruzar las reglas teóricas (Documentos 1 y 2) contra los hallazgos históricos (Documento 3):
     ```text
     Actúa como un Auditor Senior de la DPCI.
     
     Cruza la información de las 3 fuentes cargadas en este cuaderno y responde con citas textuales respaldadas por tus referencias numeradas:
     1. Compara el plazo máximo permitido en el Manual de Contratación para aprobar actas de avance frente a lo que realmente ocurrió según el Informe Histórico de Lecciones Aprendidas. ¿Cuál fue la desviación en días?
     2. Compara los incidentes reportados en el Informe Histórico frente a las prohibiciones establecidas en el Acuerdo 088 de Seguridad e IA.
     3. ¿Qué requisito adicional exige el Manual de Contratación si un proyecto supera los $100.000 USD y qué control exige el Acuerdo 088 si su informe financiero supera los $50.000 USD?
     ```
   * Haz clic sobre los números de cita generados en la respuesta de **NotebookLM** para comprobar cómo el sistema resalta el fragmento exacto en la fuente original.

4. **Redacción de materiales de capacitación interna desde NotebookLM:**
   * Manteniéndote en **NotebookLM**, utiliza el chat para transformar el conocimiento de las 3 fuentes en un módulo de entrenamiento estructurado para nuevos funcionarios de la DPCI:
     ```text
     Actúa como un Diseñador Instruccional de la DPCI.
     
     Con base exclusiva en las 3 fuentes de este cuaderno, diseña una "Guía de Inducción y Capacitación Rápida para Nuevos Supervisores de Proyectos de la DPCI" que incluya:
     1. Decálogo de Reglas de Oro (5 reglas sobre contratación y 5 reglas sobre seguridad de la información y uso de IA).
     2. Dos (2) casos prácticos cortos (escenarios de "Qué hacer / Qué no hacer") basados en los errores reales documentados en el Informe de Lecciones Aprendidas.
     3. Un cuestionario de evaluación de 4 preguntas de selección múltiple con su clave de respuestas correctas y la fuente normativa que respalda cada respuesta.
     ```
   * Haz clic en **Guardar en nota** (en la parte inferior de la respuesta de NotebookLM) para fijar este material en tu panel de estudio.

5. **Generación de recursos automáticos en Studio (NotebookLM) y validación final en Google Gemini:**
   * En el panel derecho **Studio** de **NotebookLM**, haz clic en **Documento de resumen** (o **Guía de estudio**) y observa cómo genera automáticamente un índice temático, preguntas clave y glosario de las 3 fuentes.
   * Opcionalmente, en el mismo panel **Studio**, haz clic en **Generar** dentro de la tarjeta **Resumen de audio** (*Audio Overview*) para escuchar cómo dos anfitriones de IA discuten y explican en formato pódcast las normativas y hallazgos de la DPCI.
   * Finalmente, copia la **Guía de Inducción y Capacitación** que creaste en el Paso 4, llévala de regreso a **Google Gemini** y envía este prompt de cierre:
     ```text
     Actúa como un Director de Talento Humano y Capacitación de la DPCI.
     
     Revisa esta Guía de Inducción generada en NotebookLM y redáctame el correo oficial de lanzamiento dirigido a todos los líderes de área de la DPCI, presentando el nuevo repositorio inteligente, resumiendo los 3 puntos críticos de cumplimiento normativo y adjuntando el enlace o instrucciones para realizar la evaluación.
     ```

## Resultado esperado
Un repositorio inteligente activo en **Google NotebookLM** (`Base_Conocimiento_DPCI_2026`) alimentado con 3 fuentes institucionales generadas en **Google Gemini**, un análisis cruzado de brechas con citas interactivas verificables, una **Guía de Inducción y Evaluación** guardada como nota permanente y el correo institucional de despliegue redactado en **Google Gemini**.
