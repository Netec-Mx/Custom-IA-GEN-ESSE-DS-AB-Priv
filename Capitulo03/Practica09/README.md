# Práctica 9. Carga de una base de datos masiva de la DPCI para usar Advanced Data Analysis e identificar tendencias y anomalías, y uso de la interfaz Canvas para redactar, de forma iterativa y colaborativa, el documento oficial de conclusiones técnicas

**Duración de la práctica:** 30 min

## Descripción
Los participantes utilizarán exclusivamente la versión gratuita de **OpenAI ChatGPT** aprovechando su entorno de ejecución de código **Advanced Data Analysis** (Python) para procesar datos, identificar tendencias y anomalías, y generar un informe técnico estructurado de la DPCI. 

> **Nota importante sobre herramientas:** La interfaz **Canvas** de OpenAI ya no se encuentra vigente ni disponible en la plataforma. Por esta razón, realizaremos la redacción iterativa, estructuración y refinamiento del documento oficial de conclusiones técnicas directamente mediante **prompts de formato y control de secciones** en el chat principal de ChatGPT.

---

## Sección 1: Demostración del Instructor (3 Pasos)

1. **Autogeneración y descarga de base de datos masiva en ChatGPT (Advanced Data Analysis):**
   * El instructor abre **ChatGPT** y envía el siguiente prompt para que el entorno de Python genere internamente un archivo CSV estructurado y lo entregue listo para descargar:
     ```text
     Actúa como un Científico de Datos de la DPCI.
     
     Utilizando tu entorno de análisis de datos (Python), genera una base de datos ficticia de 30 registros de ejecución contractual con las columnas: ID_Contrato, Mes, Area_Tecnica, Valor_USD, Dias_Retraso y Estado. 
     Introduce intencionalmente 2 registros con valores atípicamente altos en Dias_Retraso (> 60 días) y entrega un enlace para descargar el archivo como 'Datos_Demo_DPCI.csv'.
     ```
   * El instructor descarga el archivo `Datos_Demo_DPCI.csv`.

2. **Carga del archivo, análisis estadístico y visualización en Advanced Data Analysis:**
   * En un nuevo chat de **ChatGPT**, el instructor adjunta el archivo `Datos_Demo_DPCI.csv` y ejecuta el análisis:
     ```text
     Analiza el archivo adjunto usando Python. Calcula el valor total y promedio en USD, identifica estadísticamente los 2 registros atípicos (anomalías) en Dias_Retraso y genera un gráfico de barras descargable del Valor_USD acumulado por Area_Tecnica.
     ```

3. **Redacción estructurada del informe técnico mediante prompts de control en el chat:**
   * Como la interfaz Canvas ya no está disponible, el instructor guía la redacción paso a paso en la misma sesión:
     ```text
     Redacta el borrador formal de "Conclusiones Técnicas de Auditoría DPCI" estructurado en 3 secciones (Resumen Ejecutivo, Análisis de Hallazgos y Medidas Correctivas), integrando las cifras y anomalías encontradas.
     ```

---

## Sección 2: Práctica Guiada del Participante (30 min)

1. **Autogeneración de una base de datos masiva institucional en ChatGPT:**
   * Abre **ChatGPT** (con tu cuenta gratuita) y envía el siguiente prompt para crear un archivo de datos extenso de 50 registros operativos y financieros de la DPCI:
     ```text
     Actúa como un Ingeniero de Datos de la DPCI.
     
     Usa tu entorno de ejecución de código (Python) para crear una base de datos institucional ficticia de 50 registros (numerados del REG-001 al REG-050) sobre gestión de proyectos, compras e infraestructura con estas columnas exactas:
     - ID_Registro
     - Trimestre (Q1, Q2, Q3 o Q4)
     - Direccion_Area (Infraestructura, Planeacion, Contratacion o Sistemas)
     - Presupuesto_Asignado_USD (valores aleatorios entre $15.000 y $250.000 USD)
     - Costo_Real_USD (valores cercanos al presupuesto, pero introduce exactamente 3 anomalías graves donde el Costo_Real_USD supere en más de un 45% al Presupuesto_Asignado_USD)
     - Tiempo_Entrega_Dias (valores entre 10 y 45 días, incluyendo 2 anomalías extremas mayores a 90 días)
     
     Exporta y entrega el enlace de descarga del archivo en formato CSV llamado 'Base_Masiva_DPCI_2026.csv'.
     ```
   * Haz clic en el enlace generado y descarga `Base_Masiva_DPCI_2026.csv` en tu computadora.

2. **Carga del archivo en Advanced Data Analysis para detección de tendencias y anomalías:**
   * Abre un **Nuevo Chat** en **ChatGPT**, haz clic en el botón **+** (adjuntar archivo) y sube el archivo `Base_Masiva_DPCI_2026.csv` que acabas de descargar.
   * Envía el siguiente prompt para ejecutar la auditoría estadística completa mediante Python:
     ```text
     Actúa como un Analista Senior de Ciencia de Datos de la DPCI.
     
     Analiza el archivo adjunto 'Base_Masiva_DPCI_2026.csv' utilizando Python y entrega:
     1. Resumen Estadístico Global: Total de registros, suma de Presupuesto_Asignado_USD, suma de Costo_Real_USD, desviación presupuestal neta (en USD y porcentaje) y promedio de Tiempo_Entrega_Dias.
     2. Detección de Anomalías Financieras: Identifica en una tabla los registros exactos donde el Costo_Real_USD excede en más del 45% al Presupuesto_Asignado_USD (muestra ID, Área, Presupuesto, Costo Real y % de Sobrecosto).
     3. Detección de Anomalías Operativas: Identifica los registros cuyo Tiempo_Entrega_Dias supera los 90 días.
     4. Tendencia Trimestral: Genera una imagen gráfica PNG descargable de líneas o barras que muestre la evolución del Presupuesto Asignado vs. Costo Real por Trimestre (Q1 a Q4).
     ```
   * Revisa las tablas estadísticas y descarga la gráfica generada por ChatGPT.

3. **Redacción del Documento Oficial de Conclusiones Técnicas mediante Prompts Estructurados:**
   * Manteniéndote en la misma conversación de **ChatGPT** (aprovechando los resultados del análisis de Python), envía el siguiente prompt para iniciar la redacción formal del informe:
     ```text
     Actúa como un Redactor Técnico Senior de la DPCI.
     
     Redacta el documento formal titulado "Informe Oficial de Conclusiones Técnicas y Auditoría de Datos - DPCI 2026".
     
     Estructura el documento con estas 4 secciones obligatorias:
     1. Resumen Ejecutivo (integrando las cifras totales de presupuesto, costo real y desviación neta calculadas en el paso anterior).
     2. Análisis de Tendencias por Trimestre y Dirección (explicando el comportamiento de ejecución a lo largo de Q1 a Q4).
     3. Hallazgos de Anomalías Críticas (detallando con sus IDs exactos los casos de sobrecosto mayor al 45% y los retrasos mayores al límite operativo).
     4. Dictamen Técnico y Medidas Correctivas (3 acciones concretas de control presupuestal y operativo).
     ```

4. **Edición colaborativa e iterativa por secciones en el chat:**
   * Refina el contenido del informe enviando instrucciones específicas de mejora iterativa:
     * **Iteración 1 (Estructuración tabular):** Envía: *"Modifica únicamente la Sección 3 para convertir los hallazgos de anomalías críticas en una tabla técnica estructurada con columnas para ID, Tipo de Anomalía, Magnitud del Impacto y Nivel de Riesgo"*.
     * **Iteración 2 (Ajuste de profundidad):** Envía: *"Expande la Sección 4 agregando un responsable institucional específico y un plazo en días para cada una de las 3 medidas correctivas"*.
     * **Iteración 3 (Revisión de tono):** Envía: *"Revisa todo el texto para asegurar un tono institucional formal de la DPCI, verifica que todas las cifras coincidan exactamente con el CSV analizado y agrega al final un bloque de firmas para el Líder de Ciencia de Datos y el Director de la DPCI"*.

5. **Copia y cierre del entregable oficial:**
   * Utiliza el botón de **Copiar** en el bloque de respuesta final de ChatGPT para extraer el documento definitivo ya depurado y guárdalo en un archivo de texto o documento para su entrega oficial.

## Resultado esperado
Una base de datos masiva autogenerada (`Base_Masiva_DPCI_2026.csv`), su auditoría estadística completa y gráfica de tendencias generadas mediante **Advanced Data Analysis** (Python), y el **Informe Oficial de Conclusiones Técnicas de la DPCI** redactado, estructurado y refinado de forma iterativa mediante prompts de control en el chat de **ChatGPT**.
