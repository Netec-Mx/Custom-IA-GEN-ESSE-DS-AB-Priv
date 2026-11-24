# Práctica 1. Implementar un proceso de verificación cruzada para validar la información generada por IA e identificar posibles inconsistencias antes de incorporarla a documentos institucionales

**Duración de la práctica:** 30 min

## Descripción
Los participantes implementarán un protocolo riguroso de verificación cruzada (Cross-Verification) para auditar y validar información generada por modelos de Inteligencia Artificial antes de integrarla a documentos técnicos y administrativos de la DPCI. A partir de expedientes normativos y reportes operativos autogenerados, los asistentes aprenderán a detectar alucinaciones, cifras inventadas, inconsistencias normativas y sesgos mediante prompts de contraste directo entre **Microsoft Copilot** y **Google Gemini**[cite: 1, 2].

---

## Sección 1: Demostración del Instructor (3 Pasos)

1. **Generación de un reporte técnico inicial en Microsoft Copilot:**
   * El instructor abre **Microsoft Copilot** y envía el siguiente prompt para simular un borrador técnico institucional con datos mezclados:
     ```text
     Actúa como un Analista Técnico de la DPCI.
     
     Redacta un borrador de informe ejecutivo de 3 párrafos sobre el estado de cumplimiento presupuestal y normativo de la DPCI durante el último trimestre. 
     Incluye explícitamente:
     - 3 indicadores cuantitativos de ejecución presupuestal.
     - 2 referencias a decretos o resoluciones institucionales vigentes.
     - 1 proyección de riesgo operativo para el próximo semestre.
     ```

2. **Extracción de afirmaciones verificables en Microsoft Copilot:**
   * En la misma sesión de **Microsoft Copilot**, el instructor solicita aislar cada afirmación fáctica del texto generado para someterla a escrutinio:
     ```text
     Extrae en una tabla Markdown todas las afirmaciones fácticas, cifras, fechas y referencias normativas del borrador anterior. 
     
     Columnas requeridas: ID_Afirmacion, Tipo_Dato (Cifra / Norma / Hecho), Texto_Literal y Nivel_Riesgo_Alucinacion (Alto / Medio / Bajo).
     ```

3. **Contraste cruzado en Google Gemini (Auditoría Externa):**
   * El instructor abre **Google Gemini**, pega el borrador del Paso 1 y ejecuta el prompt de auditoría independiente:
     ```text
     Actúa como un Auditor de Calidad y Control Interno de la DPCI. 
     
     Analiza el siguiente texto generado por otra IA. Tu única tarea es detectar posibles alucinaciones, citas normativas inexistentes, inconsistencias lógicas entre cifras o afirmaciones sin sustento verificable. 
     
     Clasifica cada hallazgo como: [VERIFICABLE], [DUDOSO - REQUIERE FUENTE] o [POSIBLE ALUCINACIÓN].
     ```

---

## Sección 2: Práctica Guiada del Participante (30 min)

1. **Autogeneración de dos expedientes técnicos complejos en Microsoft Copilot:**
   * Abre **Microsoft Copilot** y envía el siguiente prompt para crear la fuente de verdad institucional con múltiples variables operativas, financieras y contractuales:
     ```text
     Actúa como un Especialista Senior de Planeación y Proyectos de la DPCI.
     
     Genera un Expediente Técnico Detallado de 450 palabras titulado "Programa Integral de Transformación Digital y Archivo Histórico de la DPCI" que contenga exactamente estos datos:
     - Presupuesto total aprobado: $780.000 USD (distribuidos en 60% infraestructura tecnológica, 25% servicios de indexación y 15% auditoría de seguridad).
     - Cronograma de ejecución: 10 meses exactos (iniciando el 15 de abril y finalizando el 15 de febrero del siguiente año).
     - Meta operativa: Digitalización y catalogación de 2.4 millones de folios físicos en 4 sedes regionales.
     - Marco normativo aplicable: Acuerdo Institucional 042 y Circular Interna 019 sobre conservación documental.
     - 3 riesgos críticos identificados: obsolescencia de escáneres de alto volumen, brechas de acceso no autorizado y retrasos en la entrega de lotes regionales.
     - Responsable técnico asignado: Subdirección de Gestión Documental e Innovación.
     ```
   * Copia y guarda este texto en un bloc de notas o documento temporal, ya que será tu **Fuente de Verdad Oficial**.

2. **Simulación de síntesis ejecutiva con sesgos e inconsistencias en Microsoft Copilot:**
   * En el mismo chat de **Microsoft Copilot**, envía el siguiente prompt para simular un escenario real donde una IA resume información extensa e introduce errores de interpretación, cálculos y omisiones:
     ```text
     Con base en el expediente anterior, redacta un "Memorando Ejecutivo para la Alta Dirección" de 180 palabras para solicitar el desembolso inicial.
     
     Para este ejercicio de entrenamiento en auditoría, introduce intencionalmente exactamente 4 inconsistencias sutiles distribuidas así:
     1. Altera ligeramente uno de los porcentajes o montos de distribución del presupuesto.
     2. Modifica la fecha de inicio o la duración en meses del cronograma.
     3. Cambia el número de folios o de sedes regionales.
     4. Inventa una norma o resolución que no estaba en el expediente original.
     
     No marques ni señales cuáles son los errores; preséntalo como si fuera un documento formal listo para firma.
     ```

3. **Auditoría cruzada línea por línea en Google Gemini:**
   * Abre **Google Gemini** en una nueva ventana del navegador.
   * Copia tanto la **Fuente de Verdad Oficial** (generada en el Paso 1) como el **Memorando Ejecutivo** (generado en el Paso 2) y pégalos debajo del siguiente prompt:
     ```text
     Actúa como un Auditor Riguroso de Calidad Documental y Control Interno de la DPCI.
     
     A continuación te entrego dos documentos: el EXPEDIENTE ORIGINAL (Fuente de Verdad) y un MEMORANDO EJECUTIVO generado por otra Inteligencia Artificial.
     
     Realiza una verificación cruzada exhaustiva comparando cada dato, cifra, fecha, norma y responsabilidad. Genera una Matriz de Auditoría en tabla Markdown con las siguientes columnas:
     - ID
     - Dato_Evaluado
     - Valor_Expediente_Original
     - Valor_Memorando_IA
     - Dictamen (COINCIDE / INCONSISTENCIA_NUMERICA / INCONSISTENCIA_TEMPORAL / ALUCINACION_NORMATIVA / OMISION)
     - Impacto_Institucional (Alto / Medio / Bajo)
     - Correccion_Exacta_Requerida
     
     Regla estricta: No asumas ni infieras información que no esté literalmente escrita en el Expediente Original.
     ```
   * Revisa la tabla generada por **Google Gemini** y verifica si logró detectar las 4 inconsistencias introducidas en el paso anterior.

4. **Validación de cálculos presupuestales y detección de omisiones en Google Gemini:**
   * En la misma conversación de **Google Gemini**, envía el siguiente prompt de profundización para auditar los cálculos derivados y los riesgos omitidos:
     ```text
     Con base en los datos del Expediente Original proporcionado anteriormente:
     
     1. Calcula exactamente cuánto dinero en USD corresponde a cada uno de los tres rubros del presupuesto ($780.000 USD distribuidos en 60%, 25% y 15%) y verifica si el Memorando Ejecutivo mencionó o alteró alguno de estos valores.
     2. Identifica qué información crítica del Expediente Original (como los 3 riesgos técnicos o el responsable asignado) fue omitida en el Memorando Ejecutivo y explica por qué esa omisión representa un riesgo administrativo para la DPCI.
     ```

5. **Reconstrucción certificada y cláusula de trazabilidad en Microsoft Copilot:**
   * Regresa a **Microsoft Copilot**, pega la **Matriz de Auditoría** y los cálculos obtenidos en **Google Gemini**, y envía el siguiente prompt para emitir la versión definitiva del documento:
     ```text
     Actúa como un Redactor Técnico Senior de la DPCI.
     
     Utilizando únicamente los datos validados del Expediente Original y corrigiendo todos los hallazgos señalados en la Matriz de Auditoría adjunta, redacta la versión definitiva del "Memorando Ejecutivo Validado para la Alta Dirección".
     
     Requisitos obligatorios del documento final:
     1. Cada cifra, fecha y norma debe incluir entre corchetes su respaldo exacto del documento fuente (ejemplo: [Ref: Expediente Técnico - Presupuesto]).
     2. Incluye un párrafo breve con los 3 riesgos operativos originales y el área responsable.
     3. Agrega al final un recuadro titulado "Certificación de Control de Calidad IA" de 4 líneas donde se deje constancia de que el texto fue sometido a verificación cruzada entre Microsoft Copilot y Google Gemini, y validado por un analista de la DPCI antes de su firma.
     ```
   * Revisa el documento final entregado y verifica que todos los datos coincidan al 100% con la fuente original.

## Resultado esperado
Una **Matriz de Auditoría de Verificación Cruzada** generada en **Google Gemini** que detecta y clasifica las inconsistencias numéricas, temporales y normativas, junto con la versión final del **Memorando Ejecutivo Validado de la DPCI** producido en **Microsoft Copilot** con citas de trazabilidad literal y su sello de control de calidad.
