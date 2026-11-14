# Práctica 5. Clasificación y categorización masiva de correspondencia, reportes o expedientes de la DPCI para la extracción automática de metadatos e indicadores estratégicos (KPIs)

**Duración de la práctica:** 30 min

## Descripción
Los participantes utilizarán herramientas de Inteligencia Artificial Generativa (**ChatGPT** y **Claude**) aprovechando sus entornos de ejecución de código para generar, importar y exportar directamente archivos descargables en formato **Microsoft Excel (.xlsx)** sin tener que copiar, pegar ni editar fórmulas manualmente en hojas de cálculo. A partir de lotes masivos de correspondencia y expedientes de la DPCI autogenerados por la IA, cada paso dependerá estrictamente del archivo o salida anterior: clasificarán documentos, calcularán indicadores estratégicos (KPIs), exportarán la base estructurada a un archivo `.xlsx` descargable y lo importarán en la segunda herramienta de IA para auditar anomalías y emitir el reporte ejecutivo final.

---

## Sección 1: Demostración del Instructor (3 Pasos)

1. **Autogeneración de correspondencia y exportación directa a archivo Excel (.xlsx) en ChatGPT:**
   * El instructor abre **ChatGPT** y envía el siguiente prompt para que la plataforma genere internamente un lote de correspondencia y entregue un archivo Excel descargable listo para usar:
     ```text
     Actúa como un Coordinador de Ventanilla Única de la DPCI.
     
     Genera un lote ficticio de 8 comunicaciones oficiales entrantes sobre trámites administrativos, jurídicos y presupuestales, extrae sus metadatos (ID_Radicado, Fecha, Area_Solicitante, Categoria_Tematica, Urgencia, Monto_USD y Plazo_Dias) y exporta directamente el resultado en un archivo descargable de Excel llamado 'Correspondencia_DPCI.xlsx'.
     ```
   * El instructor hace clic en el enlace de descarga del archivo `Correspondencia_DPCI.xlsx` generado por **ChatGPT**.

2. **Importación del archivo Excel (.xlsx) en Claude para análisis y detección de anomalías:**
   * El instructor abre **Claude**, adjunta el archivo `Correspondencia_DPCI.xlsx` recién descargado y envía el siguiente prompt:
     ```text
     Actúa como un Analista de Inteligencia de Datos de la DPCI.
     
     Analiza el archivo Excel adjunto. Clasifica los registros por nivel de criticidad, calcula el presupuesto total en Monto_USD, el promedio de Plazo_Dias e identifica si existe algún registro atípico o anomalía en los plazos o montos.
     ```

3. **Exportación de reporte consolidado desde Claude:**
   * En la misma sesión de **Claude**, el instructor solicita consolidar el diagnóstico en un formato estructurado descargable (ej. CSV o reporte técnico) para cerrar el ciclo sin edición manual en Excel:
     ```text
     Con base en el análisis anterior del archivo Excel, genera una tabla resumen de KPIs por Categoria_Tematica y redáctame un párrafo ejecutivo de conclusiones para la Dirección de la DPCI.
     ```

---

## Sección 2: Práctica Guiada del Participante (30 min)

1. **Autogeneración masiva de expedientes y exportación directa a Excel (.xlsx) en ChatGPT:**
   * Abre **ChatGPT** y envía el siguiente prompt para que genere un volumen masivo de 25 expedientes no estructurados, extraiga sus metadatos y exporte directamente el archivo Excel descargable:
     ```text
     Actúa como un Especialista de Gestión Documental e Ingeniero de Datos de la DPCI.
     
     Genera internamente un lote simulado de 25 expedientes y comunicaciones institucionales (numerados del EXP-001 al EXP-025) con datos variados de la DPCI:
     - Mes_Radicacion (Enero, Febrero o Marzo)
     - Sede_Regional (Norte, Centro, Sur u Occidente)
     - Categoria_Tramite (Contratacion, Soporte_TI, Juridico, Presupuesto o Atencion_Ciudadana)
     - Monto_USD (valores entre $0 y $150.000 USD, incluyendo 3 casos con montos atípicamente altos)
     - Dias_Sin_Respuesta (valores entre 1 y 50 días, incluyendo 4 casos críticos vencidos con más de 35 días)
     - Estado_Actual (Abierto, En_Revision o Vencido)
     
     Procesa toda esa información y expórtala directamente a un archivo de Excel descargable llamado 'Base_Expedientes_DPCI.xlsx' con una hoja llamada 'Metadatos_Extraidos'.
     ```
   * Descarga el archivo `Base_Expedientes_DPCI.xlsx` en tu computadora (no es necesario abrirlo ni editarlo manualmente en Excel).

2. **Enriquecimiento del archivo Excel con cálculos de KPIs y alertas en ChatGPT:**
   * En la misma conversación de **ChatGPT**, pídele que procese el archivo que acaba de crear para agregar indicadores estratégicos y exportar una segunda versión actualizada:
     ```text
     Toma el archivo 'Base_Expedientes_DPCI.xlsx' que acabas de generar y créame una nueva versión descargable llamada 'Base_Expedientes_KPIs_DPCI.xlsx' que incluya:
     1. En la hoja 'Metadatos_Extraidos': Una nueva columna calculada llamada 'Alerta_Anomalia' que marque "CRITICO" si Dias_Sin_Respuesta > 30 o si Monto_USD supera el promedio general, y "NORMAL" en los demás casos.
     2. Una segunda hoja llamada 'Resumen_KPIs' con una tabla consolidada que calcule: Total de Expedientes, Presupuesto Total USD, Promedio de Días sin Respuesta, Total de Casos Críticos y el desglose de presupuesto por Sede_Regional.
     ```
   * Descarga el archivo actualizado `Base_Expedientes_KPIs_DPCI.xlsx`.

3. **Importación del archivo Excel (.xlsx) en Claude para auditoría profunda de patrones y anomalías:**
   * Abre **Claude** en una nueva ventana del navegador, haz clic en el icono de adjuntar archivo (**+**) y sube el archivo `Base_Expedientes_KPIs_DPCI.xlsx` que descargaste en el paso anterior.
   * Envía el siguiente prompt para que **Claude** lea las dos hojas del libro Excel y realice el diagnóstico analítico:
     ```text
     Actúa como un Auditor de Ciencia de Datos y Control de Gestión de la DPCI.
     
     Lee completo el archivo Excel adjunto ('Base_Expedientes_KPIs_DPCI.xlsx'), revisando tanto la hoja 'Metadatos_Extraidos' como la hoja 'Resumen_KPIs'.
     
     Con base estricta en los datos contenidos en el archivo, responde:
     1. Valida si los cálculos de la hoja 'Resumen_KPIs' coinciden exactamente con los registros de la hoja 'Metadatos_Extraidos'.
     2. Identifica qué Sede_Regional y qué Categoria_Tramite concentran la mayor cantidad de expedientes marcados como "CRITICO".
     3. Lista los 5 expedientes con mayor riesgo operativo/financiero (indicando su ID, Sede, Monto_USD y Dias_Sin_Respuesta) y explica qué patrón de anomalía presentan.
     ```

4. **Generación de informe ejecutivo descargable desde Claude a partir del Excel:**
   * Manteniéndote en la misma sesión de **Claude** (donde sigue cargado el archivo `Base_Expedientes_KPIs_DPCI.xlsx`), solicita redactar y exportar el informe técnico consolidado:
     ```text
     Actúa como el Director de Planeación de la DPCI.
     
     Utilizando exclusivamente los datos y KPIs extraídos del archivo Excel adjunto, redacta un "Informe Ejecutivo de Inteligencia Documental y Control de KPIs" listo para presentar al Comité Directivo.
     
     Estructura el informe en:
     1. Tablero Ejecutivo de Indicadores (presentando los KPIs globales en una tabla limpia).
     2. Diagnóstico de Anomalías por Sede Regional y Categoría.
     3. Tres (3) Recomendaciones Estratégicas basadas en evidencia numérica para descongestionar los trámites críticos.
     ```

5. **Importación del Excel en ChatGPT para generación de visualización gráfica descargable:**
   * Regresa a **ChatGPT** (en la sesión donde está `Base_Expedientes_KPIs_DPCI.xlsx` o subiendo el archivo nuevamente) y solicita generar un gráfico ejecutivo listo para descargar e insertar en reportes:
     ```text
     Con base en los datos del archivo 'Base_Expedientes_KPIs_DPCI.xlsx', genera un gráfico ejecutivo combinado de alta resolución (en formato PNG descargable) que muestre:
     - En un panel izquierdo: El Presupuesto Total en USD por Sede_Regional (gráfico de barras).
     - En un panel derecho: La distribución porcentual de expedientes según su estado en 'Alerta_Anomalia' (CRITICO vs NORMAL).
     
     Asegúrate de incluir etiquetas de datos claras y títulos institucionales de la DPCI.
     ```
   * Descarga la imagen gráfica generada como evidencia visual del análisis.

## Resultado esperado
Un flujo de trabajo automatizado sin manipulación manual de hojas de cálculo: generación y exportación directa del archivo **Excel** (`Base_Expedientes_KPIs_DPCI.xlsx`) desde **ChatGPT**, importación y auditoría cruzada de patrones y anomalías en **Claude**, emisión del **Informe Ejecutivo de KPIs** y exportación de un **Gráfico Analítico en PNG** listo para presentación institucional.
