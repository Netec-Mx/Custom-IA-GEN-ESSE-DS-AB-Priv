# Práctica 10. Analizar un conjunto de documentos relacionados con un mismo expediente utilizando Claude para identificar hechos relevantes, detectar inconsistencias entre documentos y generar un informe técnico consolidado con evidencia y conclusiones

**Duración de la práctica:** 30 min

## Descripción
Los participantes utilizarán exclusivamente la versión gratuita de **Anthropic Claude** aprovechando su amplia ventana de contexto, su precisión analítica sobre textos extensos y su capacidad de generación estructurada (incluyendo *Artifacts* para documentos limpios) para auditar un expediente multi-documental complejo de la DPCI. A partir de un conjunto de documentos interrelacionados 100% autogenerados dentro de la misma sesión (sin exceder la cuota gratuita de mensajes), los asistentes extraerán hechos relevantes, cruzarán evidencia para detectar inconsistencias ocultas entre áreas y consolidarán un informe técnico oficial listo para su descarga o entrega.

> **Nota técnica para el aula (Versión Gratuita de Claude):** En el plan gratuito de Claude, la función de *Proyectos (Projects)* suele estar reservada para planes de pago, por lo que en esta práctica simularemos un entorno de expediente consolidado dentro de **una única conversación de ventana de contexto extensa** (manteniendo todos los documentos activos en la misma sesión y aprovechando *Artifacts* en panel lateral derecho).

---

## Sección 1: Demostración del Instructor (3 Pasos)

1. **Autogeneración de un expediente multi-documental en Claude:**
   * El instructor abre **Claude** y envía el siguiente prompt para crear tres documentos internos sobre un mismo caso institucional con una contradicción intencional:
     ```text
     Actúa como un Coordinador de Archivo Central de la DPCI.
     
     Genera 3 documentos breves (120 palabras cada uno) pertenecientes al expediente "CASO-DPCI-901: Adquisición de Servidores de Respaldo":
     - DOC A (Especificación Técnica TI): Solicita 4 servidores rack de 64 GB RAM con entrega máxima el 15 de octubre.
     - DOC B (Orden de Compra Administrativa): Autoriza la compra de 4 servidores rack de 32 GB RAM por un valor de $80.000 USD.
     - DOC C (Acta de Recepción de Almacén): Certifica que el 22 de octubre se recibieron 3 servidores conforme a lo solicitado.
     ```

2. **Extracción de hechos relevantes y detección cruzada de inconsistencias en Claude:**
   * En la misma sesión de **Claude**, el instructor ejecuta el prompt de auditoría cruzada para aislar evidencias y contradicciones:
     ```text
     Actúa como un Auditor Forense Documental de la DPCI.
     
     Analiza conjuntamente los 3 documentos del CASO-DPCI-901 que acabas de generar y construye una tabla Markdown con las columnas: Aspecto_Evaluado, Evidencia_DOC_A, Evidencia_DOC_B, Evidencia_DOC_C y Dictamen (CONSISTENTE / INCONSISTENCIA_TECNICA / INCONSISTENCIA_CANTIDAD / RETRASO_TEMPORAL).
     ```

3. **Generación de informe técnico consolidado en panel lateral (Artifact) de Claude:**
   * El instructor solicita consolidar el dictamen en un documento formal limpio dentro del panel lateral derecho de Claude:
     ```text
     Con base en la auditoría anterior, redacta un "Dictamen Técnico de No Conformidad Contractual" de 3 secciones (Hechos Relevantes, Matriz de Inconsistencias con Evidencia y Conclusiones Jurídico-Técnicas) preséntalo como un documento limpio y estructurado listo para copiar o descargar.
     ```

---

## Sección 2: Práctica Guiada del Participante (30 min)

1. **Autogeneración del expediente completo de 5 documentos interrelacionados en Claude:**
   * Abre **Claude** (con tu cuenta gratuita en una conversación nueva) y envía el siguiente prompt para generar un expediente extenso compuesto por 5 piezas documentales de distintas áreas de la DPCI con inconsistencias ocultas entre sí:
     ```text
     Actúa como un Gestor de Expedientes Complejos de la DPCI.
     
     Genera un expediente institucional extenso compuesto por 5 documentos oficiales (de unas 160 palabras cada uno) relacionados con un mismo caso titulado "EXPEDIENTE DPCI-2026-550: Implementación del Sistema de Monitoreo Regional":
     
     - DOCUMENTO 1 (Estudio Previo - Dirección de Planeación, fecha 10 de febrero): Define el alcance para 6 sedes regionales, presupuesto estimado de $320.000 USD, plazo de 5 meses (entrega final el 10 de julio) y exige certificación ISO 27001 obligatoria al proveedor.
     - DOCUMENTO 2 (Propuesta Adjudicada - Proveedor TechGlobal, fecha 25 de febrero): Oferta implementar el sistema en 6 sedes regionales por $320.000 USD, plazo de 5 meses, pero aclara en una nota al pie que su certificación ISO 27001 está "en trámite" y que el soporte técnico en sitio solo cubre 4 de las 6 sedes.
     - DOCUMENTO 3 (Contrato Firmado - Oficina Jurídica, fecha 05 de marzo): Establece un valor contractual de $345.000 USD (sin justificar el incremento de $25.000 USD), fecha de entrega el 10 de julio y multa del 2% semanal por retraso.
     - DOCUMENTO 4 (Informe de Interventoría - Supervisión Técnica, fecha 20 de julio): Reporta que a la fecha el sistema solo opera en 4 sedes regionales, presenta fallas de sincronización y aún no se ha entregado la certificación ISO 27001.
     - DOCUMENTO 5 (Solicitud de Pago Total - Área Financiera, fecha 25 de julio): Tramita el desembolso del 100% del contrato ($345.000 USD) alegando "cumplimiento a satisfacción según cronograma".
     
     Separa claramente cada documento con su encabezado completo.
     ```
   * Lee brevemente los 5 documentos generados para familiarizarte con el contexto del caso.

2. **Extracción cronológica de hechos relevantes y trazabilidad documental en Claude:**
   * Manteniéndote en la misma conversación de **Claude** (aprovechando su ventana de contexto), envía el siguiente prompt para reconstruir la línea de tiempo oficial del expediente con citas literales de evidencia:
     ```text
     Actúa como un Investigador y Analista Documental Senior de la DPCI.
     
     Procesa la totalidad de los 5 documentos del EXPEDIENTE DPCI-2026-550 generados en el paso anterior y extrae todos los hechos relevantes ordenados cronológicamente.
     
     Construye una Matriz de Hechos y Evidencia en tabla Markdown con las siguientes columnas:
     - Fecha_Documento
     - Documento_Fuente (DOC 1 a DOC 5)
     - Area_o_Actor_Emisor
     - Hecho_Relevante_Compromiso
     - Cita_Literal_Clave (fragmento exacto que respalda el dato o cifra)
     
     Regla estricta: No omitas ningún documento ni alteres fechas o cifras.
     ```

3. **Auditoría cruzada exhaustiva para detección de inconsistencias entre documentos en Claude:**
   * En la misma sesión de **Claude**, ejecuta el prompt de confrontación entre documentos para identificar todas las contradicciones financieras, técnicas, contractuales y de cumplimiento:
     ```text
     Actúa como un Auditor Jefe de Control Interno y Cumplimiento de la DPCI.
     
     Cruza sistemáticamente la información de los 5 documentos del EXPEDIENTE DPCI-2026-550 entre sí e identifica TODAS las inconsistencias, omisiones o irregularidades existentes.
     
     Agrupa tus hallazgos en una Matriz de Inconsistencias en tabla Markdown con las columnas:
     - ID_Hallazgo
     - Dimension (Financiera / Alcance_Tecnico / Cumplimiento_Normativo / Temporal_Cronograma / Control_Pagos)
     - Documentos_en_Conflicto (ejemplo: DOC 1 vs DOC 3)
     - Descripcion_Exacta_de_la_Inconsistencia (citando cifras y fechas exactas de ambos documentos)
     - Nivel_Gravedad (Critico / Alto / Medio)
     - Riesgo_Patrimonial_o_Legal_para_la_DPCI
     ```
   * Verifica que Claude haya detectado las 5 brechas principales (incremento injustificado de $25.000 USD, ausencia de ISO 27001, cobertura en solo 4 de 6 sedes, retraso respecto al 10 de julio e intento de pago del 100% sin cumplimiento).

4. **Redacción del Informe Técnico Consolidado con Evidencia y Conclusiones en Claude:**
   * En la misma conversación, solicita a **Claude** consolidar todo el análisis en un entregable técnico definitivo de alto nivel (se abrirá automáticamente como documento estructurado en el panel lateral derecho / *Artifact*):
     ```text
     Actúa como el Director Técnico de Auditoría y Evaluación de Proyectos de la DPCI.
     
     Con base exclusiva en los 5 documentos del EXPEDIENTE DPCI-2026-550 y en las matrices de hechos e inconsistencias obtenidas en los pasos anteriores, redacta el documento oficial titulado: "INFORME TÉCNICO CONSOLIDADO DE AUDITORÍA DOCUMENTAL - EXPEDIENTE DPCI-2026-550".
     
     Estructura el informe de manera impecable con estas 5 secciones:
     1. Identificación del Expediente y Objeto de la Revisión.
     2. Síntesis Cronológica de Hechos Relevantes (resumiendo la trazabilidad del 10 de febrero al 25 de julio).
     3. Análisis Detallado de Inconsistencias con Evidencia Documental (presentando cada inconsistencia respaldada con citas exactas de los documentos involucrados).
     4. Conclusiones Técnicas y Determinación de Responsabilidades (dictaminando si procede o no el pago solicitado en el DOC 5 y el cálculo de penalidades aplicables según el DOC 3).
     5. Recomendaciones Vinculantes (4 acciones inmediatas dirigidas a Jurídica, Financiera, Interventoría y Planeación).
     ```

5. **Refinamiento final, validación de citas y exportación del informe desde Claude:**
   * Revisa el documento generado en el panel derecho de **Claude** y envía un último prompt corto de verificación de calidad antes de descargarlo:
     ```text
     Revisa el Informe Técnico Consolidado que acabas de generar y verifica que:
     1. Todas las cifras en USD ($320.000 y $345.000) y fechas (10 feb, 25 feb, 05 mar, 10 jul, 20 jul, 25 jul) sean 100% coherentes en todo el texto.
     2. Agrega al final un "Anexo de Trazabilidad" con una lista de verificación de 5 puntos firmada por el Equipo Auditor de la DPCI.
     ```
   * Utiliza el botón **Copiar** o **Descargar** en la esquina inferior/superior derecha del documento en **Claude** para guardar tu informe técnico consolidado.

## Resultado esperado
Un expediente multi-documental complejo de 5 piezas procesado íntegramente en la ventana de contexto de **Claude**, una **Matriz Cronológica de Hechos y Evidencia**, una **Matriz de Inconsistencias Cruzadas** entre áreas y un **Informe Técnico Consolidado** formalizado en el panel de documentos de **Claude** listo para entrega institucional.
