# Práctica 7. Análisis automático de un archivo de Excel institucional con Copilot; generación de un informe ejecutivo estructurado en Word (objetivos, alcances, políticas, métricas y glosario) y creación automatizada de su presentación en PowerPoint

**Duración de la práctica:** 30 min

## Descripción
Los participantes utilizarán exclusivamente **Microsoft Copilot Chat** (sin depender de licencias integradas dentro de las aplicaciones de escritorio de Office) para ejecutar un flujo completo de análisis y generación documental institucional de la DPCI. A partir de una base de datos presupuestal y operativa autogenerada directamente en un archivo Excel descargable (`.xlsx`), los asistentes analizarán métricas clave, generarán la estructura completa de un informe ejecutivo (objetivos, alcances, políticas, métricas y glosario) exportable a Word (`.docx`) y producirán el guión estructurado y descargable para su presentación en PowerPoint (`.pptx`).

---

## Sección 1: Demostración del Instructor (3 Pasos)

1. **Autogeneración de archivo Excel institucional descargable en Microsoft Copilot Chat:**
   * El instructor abre **Microsoft Copilot Chat** y envía el siguiente prompt para que la herramienta genere internamente datos operativos y entregue un libro `.xlsx` listo para descargar:
     ```text
     Actúa como un Analista de Planeación de la DPCI.
     
     Genera internamente una base de datos ficticia de 10 proyectos institucionales con las columnas: ID_Proyecto, Area_Responsable, Presupuesto_Asignado_USD, Presupuesto_Ejecutado_USD, Avance_Fisico_Pct y Estado (En_Curso, Retrasado, Finalizado).
     
     Exporta directamente esta tabla a un archivo de Excel descargable llamado 'Seguimiento_Proyectos_DPCI.xlsx'.
     ```
   * El instructor descarga el archivo `Seguimiento_Proyectos_DPCI.xlsx`.

2. **Análisis automático de indicadores y anomalías en Microsoft Copilot Chat:**
   * En la misma sesión de **Microsoft Copilot Chat**, el instructor solicita auditar los datos del archivo recién creado sin abrir Excel:
     ```text
     Analiza el archivo 'Seguimiento_Proyectos_DPCI.xlsx' que acabas de generar y responde en una tabla resumen:
     
     1. Total de presupuesto asignado vs. ejecutado en USD.
     2. Porcentaje global de ejecución financiera.
     3. Identifica cuáles son los proyectos en estado "Retrasado" que presentan mayor desviación presupuestal.
     ```

3. **Generación de estructura de Informe Ejecutivo y esquema de Presentación en Microsoft Copilot Chat:**
   * El instructor solicita transformar el análisis anterior en los insumos documentales listos para llevar a Word y PowerPoint:
     ```text
     Con base en el análisis del archivo Excel, redacta:
     
     1. Un bloque estructurado para Informe Ejecutivo en Word con: Objetivos, Alcance y Métricas Clave.
     2. Un esquema de 3 diapositivas para PowerPoint indicando título, 3 viñetas ejecutivas y sugerencia visual por diapositiva.
     ```

---

## Sección 2: Práctica Guiada del Participante (30 min)

1. **Autogeneración del archivo Excel institucional de gestión y contratación en Microsoft Copilot Chat:**
   * Abre **Microsoft Copilot Chat** y envía el siguiente prompt para crear una base de datos robusta de 20 registros operativos de la DPCI y exportarla directamente como archivo `.xlsx` descargable:
     ```text
     Actúa como un Especialista de Control de Gestión y Presupuesto de la DPCI.
     
     Genera internamente una base de datos institucional ficticia de 20 registros operativos (numerados del PRY-001 al PRY-020) con las siguientes columnas exactas:
     - ID_Proyecto
     - Direccion_Solicitante (Infraestructura, Contratacion, Planeacion_Estrategica o Tecnologia)
     - Tipo_Contrato (Obra_Publica, Consultoria, Suministro_TI o Interventoria)
     - Presupuesto_Aprobado_USD (valores entre $25.000 y $300.000 USD)
     - Monto_Ejecutado_USD (valores coherentes con el presupuesto aprobado, incluyendo 3 casos con sobreejecución o alerta financiera)
     - Porcentaje_Avance (valores entre 10% y 100%)
     - Nivel_Riesgo (Alto, Medio o Bajo)
     
     Exporta esta base de datos directamente en un archivo de Excel descargable llamado 'Gestion_Contractual_DPCI.xlsx' con una hoja llamada 'Base_Datos_2026'.
     ```
   * Descarga el archivo `Gestion_Contractual_DPCI.xlsx` en tu equipo para verificar su generación.

2. **Análisis automático de métricas, tendencias y riesgos sobre el Excel en Microsoft Copilot Chat:**
   * Manteniéndote en la misma conversación de **Microsoft Copilot Chat** (donde está cargado el archivo `Gestion_Contractual_DPCI.xlsx`), envía el siguiente prompt para extraer el diagnóstico cuantitativo que alimentará el informe oficial:
     ```text
     Actúa como un Auditor Financiero y Científico de Datos de la DPCI.
     
     Analiza completamente la hoja 'Base_Datos_2026' del archivo 'Gestion_Contractual_DPCI.xlsx' y calcula con exactitud:
     1. Tabla de Métricas por Dirección Solicitante: Total de proyectos, Presupuesto Aprobado Total (USD), Monto Ejecutado Total (USD) y Saldo Disponible (USD).
     2. Análisis por Tipo de Contrato: Promedio de Porcentaje_Avance y conteo de proyectos con Nivel_Riesgo "Alto".
     3. Detección de Anomalías: Lista los IDs de los proyectos donde el Monto_Ejecutado_USD supere el 90% del Presupuesto_Aprobado_USD pero su Porcentaje_Avance sea inferior al 60%, explicando el riesgo financiero que esto representa para la DPCI.
     ```

3. **Generación del Informe Ejecutivo estructurado para Word en Microsoft Copilot Chat:**
   * En la misma sesión de **Microsoft Copilot Chat**, tomando estrictamente como base el archivo Excel y los cálculos del Paso 2, solicita redactar y exportar el documento formal con las cinco secciones institucionales requeridas:
     ```text
     Actúa como un Redactor Técnico Senior y Asesor de Dirección de la DPCI.
     
     Con base exclusiva en los datos del archivo 'Gestion_Contractual_DPCI.xlsx' y en el análisis financiero realizado anteriormente, redacta un "Informe Ejecutivo Institucional de Seguimiento Contractual y Presupuestal" completamente estructurado en estas 5 secciones obligatorias:
     1. Objetivos (Objetivo general y 3 objetivos específicos del seguimiento).
     2. Alcances (Cobertura temporal, direcciones evaluadas y universo de contratos analizados).
     3. Políticas Institucionales de Control (4 lineamientos obligatorios de gobernanza presupuestal y mitigación de riesgos aplicables a los hallazgos).
     4. Métricas y Resultados Clave (Incluyendo las tablas resumen calculadas en el paso anterior y el detalle de las anomalías detectadas).
     5. Glosario Técnico (Definición clara de 6 términos clave utilizados en el informe: Ejecución Presupuestal, Saldo Disponible, Riesgo Contractual, Desviación Financiera, Avance Físico e Interventoría).
     
     Si tu entorno lo permite, genera un archivo descargable de Word llamado 'Informe_Ejecutivo_DPCI.docx' con este contenido; adicionalmente, preséntalo completo y formateado en el chat.
     ```

4. **Creación automatizada de la estructura y contenido de Presentación para PowerPoint en Microsoft Copilot Chat:**
   * En la misma conversación de **Microsoft Copilot Chat**, solicita transformar el informe ejecutivo del Paso 3 en un guión completo de diapositivas listo para presentar ante la Alta Dirección:
     ```text
     Actúa como un Consultor de Comunicación Ejecutiva para la Alta Dirección de la DPCI.
     
     Transforma el "Informe Ejecutivo Institucional" generado en el paso anterior en una presentación ejecutiva de 6 diapositivas dirigida al Comité Directivo:
     - Diapositiva 1: Portada Institucional (Título, subtítulo, área emisora y fecha).
     - Diapositiva 2: Objetivos y Alcance de la Auditoría Presupuestal.
     - Diapositiva 3: Tablero de Métricas Financieras por Dirección Solicitante (datos exactos en tabla resumida).
     - Diapositiva 4: Desempeño por Tipo de Contrato y Mapa de Riesgos Altos.
     - Diapositiva 5: Alertas Críticas y Anomalías Detectadas (proyectos con alta ejecución financiera y bajo avance físico).
     - Diapositiva 6: Políticas de Control y Plan de Acción Inmediato.
     
     Para cada diapositiva entrega: Título impactante, máximo 4 viñetas ejecutivas concisas (sin párrafos largos), sugerencia de gráfico o elemento visual a incluir y notas breves del orador. Si tu entorno lo permite, expórtalo como archivo descargable 'Presentacion_Comite_DPCI.pptx'.
     ```

5. **Validación cruzada de consistencia numérica entre Excel, Informe y Presentación en Microsoft Copilot Chat:**
   * Para cerrar el flujo en **Microsoft Copilot Chat**, ejecuta un prompt de auditoría final que garantice que no hubo pérdida ni alteración de cifras al pasar del Excel al informe y a las diapositivas:
     ```text
     Actúa como un Auditor de Control Interno de la DPCI.
     
     Realiza una verificación de trazabilidad cruzando las cifras originales de 'Gestion_Contractual_DPCI.xlsx' contra los datos incluidos en el Informe Ejecutivo (Paso 3) y en la Presentación de 6 diapositivas (Paso 4).
     
     Entrega una tabla de control de calidad con 4 indicadores globales (Total Proyectos, Presupuesto Total Aprobado, Monto Total Ejecutado y Total Proyectos en Riesgo Alto) mostrando su valor en el Excel, su valor en el Informe, su valor en la Presentación y el estado final (CONCILIADO / DISCREPANCIA).
     ```

## Resultado esperado
Un flujo documental completo ejecutado desde **Microsoft Copilot Chat**: la base de datos descargable en **Excel** (`Gestion_Contractual_DPCI.xlsx`), el análisis de métricas y anomalías, el **Informe Ejecutivo** estructurado en 5 secciones (Objetivos, Alcances, Políticas, Métricas y Glosario) listo o exportado para **Word**, el esquema completo de 6 diapositivas para **PowerPoint** y la tabla final de conciliación numérica.
