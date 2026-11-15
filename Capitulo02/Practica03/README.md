# Práctica 3. Diseñar prompts para resumir, clasificar, comparar y analizar grandes conjuntos de documentos relacionados con un mismo caso

**Duración de la práctica:** 30 min

## Descripción
Los participantes aplicarán técnicas avanzadas de ingeniería de prompts (estructuración por bloques, *Few-Shot Prompting* y *Chain of Thought*) para procesar, sintetizar, clasificar, comparar y analizar múltiples documentos asociados a un mismo expediente institucional de la DPCI. Utilizando información 100% autogenerada y combinando **Claude** y **Google Gemini**, los asistentes transformarán información dispersa y no estructurada en matrices comparativas y dictámenes analíticos consistentes.

---

## Sección 1: Demostración del Instructor (3 Pasos)

1. **Autogeneración de un expediente multi-documental en Claude:**
   * El instructor abre **Claude** y envía el siguiente prompt para simular tres documentos distintos pertenecientes a un mismo caso institucional:
     ```text
     Actúa como un Coordinador de Gestión Documental de la DPCI.
     
     Genera 3 documentos breves (de unas 100 palabras cada uno) asociados al mismo expediente "Caso DPCI-2026-089: Actualización de Infraestructura de Red":
     - DOCUMENTO A (Solicitud Técnica del Área de TI): Justifica la compra urgente de equipos y especifica un presupuesto estimado de $120.000 USD.
     - DOCUMENTO B (Concepto Presupuestal de Finanzas): Aprueba únicamente $95.000 USD y condiciona el desembolso a entregas en dos fases.
     - DOCUMENTO C (Acta de Seguimiento de Riesgos): Advierte que dividir la entrega en dos fases retrasará 45 días la entrada en operación.
     ```

2. **Clasificación y extracción estructurada mediante Few-Shot Prompting en Claude:**
   * En la misma sesión de **Claude**, el instructor demuestra cómo guiar el formato exacto de salida mediante ejemplos (*Few-Shot*):
     ```text
     Clasifica y extrae la información clave de los 3 documentos anteriores siguiendo exactamente este formato de ejemplo:
     
     Ejemplo de salida esperada:
     [ID_Doc]: DOC-X | [Area_Emisora]: Nombre del área | [Postura_Principal]: Resumen en 10 palabras | [Impacto_Clave]: Cifra o plazo crítico.
     
     Aplica este mismo patrón para los Documentos A, B y C.
     ```

3. **Análisis comparativo con Chain of Thought (Cadena de Pensamiento) en Google Gemini:**
   * El instructor abre **Google Gemini**, pega los 3 documentos del Paso 1 y ejecuta un prompt de razonamiento paso a paso:
     ```text
     Actúa como un Analista Senior de Proyectos de la DPCI.
     
     Analiza conjuntamente los Documentos A, B y C del Caso DPCI-2026-089. Antes de dar tu conclusión, razona paso a paso (Chain of Thought):
     1. Compara las cifras económicas entre el Documento A y el Documento B.
     2. Cruza la condición financiera del Documento B con la alerta operativa del Documento C.
     3. Identifica el cuello de botella principal del expediente.
     4. Emite una recomendación ejecutiva de 3 líneas para destrabar el caso.
     ```

---

## Sección 2: Práctica Guiada del Participante (30 min)

1. **Autogeneración de un paquete documental complejo de un mismo caso en Claude:**
   * Abre **Claude** y envía el siguiente prompt para crear 4 documentos institucionales interrelacionados con diferentes enfoques técnicos, legales y operativos:
     ```text
     Actúa como un Especialista de Operaciones de la DPCI.
     
     Genera un conjunto de 4 documentos ficticios (de unas 130 palabras cada uno) relacionados con un mismo proyecto institucional titulado "Expediente DPCI-404: Implementación de Plataforma de Atención Ciudadana Digital":
     - DOC 1 (Requerimiento Funcional - Área de Servicio): Solicita cobertura 24/7, integración con 3 bases de datos internas y lanzamiento en 4 meses.
     - DOC 2 (Evaluación de Arquitectura - Área de TI): Indica que la integración con las 3 bases de datos requiere 6 meses de desarrollo y un equipo adicional de 2 ingenieros.
     - DOC 3 (Informe de Cotización - Área de Compras): Presenta dos opciones de proveedores: Proveedor Alfa ($180.000 USD, entrega en 5 meses, sin soporte 24/7 incluido) y Proveedor Beta ($230.000 USD, entrega en 4 meses, soporte 24/7 incluido).
     - DOC 4 (Concepto Jurídico - Oficina Legal): Advierte que el contrato debe incluir cláusulas estrictas de confidencialidad y penalidad del 10% por cada mes de retraso en el lanzamiento.
     
     Separa claramente cada documento con su título.
     ```
   * Copia y guarda los 4 documentos en un bloc de notas temporal como tu **Expediente Base DPCI-404**.

2. **Resumen ejecutivo multinivel mediante prompts estructurados en Claude:**
   * En la misma conversación de **Claude**, envía el siguiente prompt diseñado con estructura de Rol, Contexto, Tarea y Restricciones para sintetizar el paquete documental:
     ```text
     Rol: Eres un Asesor Ejecutivo de la Dirección General de la DPCI.
     Contexto: Tienes a la vista los 4 documentos del Expediente DPCI-404 generados anteriormente.
     Tarea: Elabora un resumen ejecutivo estructurado en dos niveles:
     - Nivel 1 (Síntesis Ultra-Corta): Un único párrafo de máximo 50 palabras que resuma el objetivo del proyecto, el rango presupuestal y el principal conflicto entre áreas.
     - Nivel 2 (Desglose por Documento): Una lista con viñetas donde cada documento (DOC 1 a DOC 4) se resuma en exactamente dos líneas: primera línea para el aporte/solicitud, segunda línea para la restricción o condición impuesta.
     Restricción: No inventes cifras ni agregues información externa al texto.
     ```

3. **Clasificación taxonómica y extracción de metadatos con Few-Shot Prompting en Google Gemini:**
   * Abre **Google Gemini** en una nueva ventana del navegador.
   * Copia el **Expediente Base DPCI-404** (los 4 documentos del Paso 1) y pégalo debajo del siguiente prompt:
     ```text
     Actúa como un Arquitecto de Información de la DPCI.
     
     Clasifica cada uno de los 4 documentos adjuntos dentro de una matriz estructurada. Utiliza la siguiente lógica de clasificación demostrada en este ejemplo:
     
     Ejemplo de referencia:
     - Documento: DOC-Ejemplo | Dimensión: Financiera | Tipo_Acto: Aprobación Presupuestal | Variable_Crítica: $50.000 USD | Nivel_Urgencia: Alto
     
     Ahora genera una tabla Markdown con las columnas: Documento, Dimension (Operativa / Tecnica / Comercial / Legal), Tipo_Acto, Variable_Critica_Numerica y Nivel_Urgencia (Critico / Alto / Medio) para DOC 1, DOC 2, DOC 3 y DOC 4.
     ```

4. **Análisis comparativo de contradicciones y escenarios mediante Chain of Thought en Google Gemini:**
   * En la misma sesión de **Google Gemini**, envía el siguiente prompt para obligar al modelo a cruzar variables y detectar inconsistencias entre las áreas de la DPCI:
     ```text
     Actúa como un Líder de Planeación Estratégica de la DPCI.
     
     Compara y analiza de forma integral los 4 documentos del Expediente DPCI-404 aplicando razonamiento paso a paso (Chain of Thought):
     - Paso 1 (Cruce de Tiempos): Compara el plazo exigido por Servicio (DOC 1), la estimación interna de TI (DOC 2) y los tiempos de los Proveedores Alfa y Beta (DOC 3). ¿Dónde existe una contradicción operativa?
     - Paso 2 (Cruce de Alcance y Costo): Compara el requisito de soporte 24/7 del DOC 1 frente a las ofertas del DOC 3 y el impacto de la penalidad legal del 10% del DOC 4.
     - Paso 3 (Matriz Comparativa de Decisión): Construye una tabla comparando "Ejecución con Proveedor Alfa" vs "Ejecución con Proveedor Beta" evaluando: Costo Total, Cumplimiento de Plazo, Cumplimiento de Soporte 24/7 y Exposición a Penalidad Legal.
     ```

5. **Generación de dictamen consolidado de resolución en Claude:**
   * Regresa a **Claude**, pega la **Matriz Comparativa de Decisión** generada en **Google Gemini** en el paso anterior, y envía el siguiente prompt para emitir el documento técnico final:
     ```text
     Actúa como el Comité Técnico de Evaluación de la DPCI.
     
     Con base en los 4 documentos originales del Expediente DPCI-404 y el análisis comparativo adjunto, redacta un "Dictamen Técnico de Resolución de Expediente" de 3 secciones:
     1. Diagnóstico de Inconsistencias Internas (resumiendo las brechas entre Servicio, TI, Compras y Legal).
     2. Opción Recomendada y Justificación Técnica-Financiera (eligiendo entre Proveedor Alfa o Beta y explicando cómo mitigar las brechas restantes).
     3. Tres (3) Acuerdos Obligatorios que deben firmar las áreas internas antes de iniciar la contratación.
     ```

## Resultado esperado
Un conjunto estructurado de prompts reutilizables aplicados sobre un expediente multi-documental de la DPCI, obteniendo como entregables una **Matriz de Clasificación Taxonómica (Few-Shot)**, una **Tabla Comparativa de Escenarios (Chain of Thought)** en **Google Gemini** y un **Dictamen Técnico Consolidado** en **Claude**.
