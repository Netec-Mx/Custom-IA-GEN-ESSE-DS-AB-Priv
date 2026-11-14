# Práctica 9. Carga de una base de datos masiva de la DPCI para usar Advanced Data Analysis e identificar tendencias y anomalías, y uso de la interfaz Canvas para redactar, de forma iterativa y colaborativa, el documento oficial de conclusiones técnicas

**Duración de la práctica:** 30 min

## Descripción
Los participantes utilizarán exclusivamente la versión gratuita de **OpenAI ChatGPT** aprovechando sus dos entornos especializados: **Advanced Data Analysis** (entorno de ejecución de código Python para procesar datos y generar gráficas) y la interfaz **Canvas** (editor colaborativo en pantalla dividida). A partir de una base de datos masiva de la DPCI autogenerada directamente en formato CSV/Excel descargable, los asistentes realizarán un análisis estadístico para identificar tendencias y anomalías, y luego activarán **Canvas** para redactar, editar por secciones y pulir de forma iterativa el documento oficial de conclusiones técnicas.

> **Nota técnica para el aula (Versión Gratuita de ChatGPT):** La versión gratuita incluye cuotas periódicas de uso para análisis de archivos con Python y apertura de Canvas. Para optimizar el consumo de mensajes en los 30 minutos de clase, cada prompt está diseñado para ejecutar múltiples tareas consolidadas por turno.

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
   * En un nuevo chat de **ChatGPT**, el instructor adjunta el archivo `Datos_Demo_DPCI.csv` (botón **+** > *Cargar desde la computadora*) y ejecuta el análisis:
     ```text
     Analiza el archivo adjunto usando Python. Calcula el valor total y promedio en USD, identifica estadísticamente los 2 registros atípicos (anomalías) en Dias_Retraso y genera un gráfico de barras descargable del Valor_USD acumulado por Area_Tecnica.
     ```

3. **Apertura de interfaz Canvas y edición iterativa del informe:**
   * En la misma sesión, el instructor solicita abrir el editor colaborativo **Canvas** (o hace clic en el icono **Canvas** en la barra de herramientas del cuadro de texto):
     ```text
     Abre Canvas y redacta un borrador corto de "Conclusiones Técnicas de Auditoría DPCI" (3 párrafos) integrando las cifras y anomalías encontradas en el archivo anterior.
     ```
   * Con la pantalla dividida de **Canvas** abierta a la derecha, el instructor selecciona el segundo párrafo con el ratón y usa el menú flotante de edición puntual para pedirle: *"Haz este párrafo más técnico y resalta los IDs de las anomalías en negrita"*.

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

3. **Apertura de la interfaz Canvas para redactar el Documento Oficial de Conclusiones Técnicas:**
   * Manteniéndote en la misma conversación de **ChatGPT** (donde están los resultados del análisis de Python), activa la herramienta **Canvas** (desde el menú de herramientas **+** > *Canvas* o solicitándolo explícitamente en el prompt) y envía:
     ```text
     Abre la interfaz Canvas y redacta el documento formal titulado "Informe Oficial de Conclusiones Técnicas y Auditoría de Datos - DPCI 2026".
     
     Estructura el documento dentro de Canvas con estas 4 secciones obligatorias:
     1. Resumen Ejecutivo (integrando las cifras totales de presupuesto, costo real y desviación neta calculadas en el paso anterior).
     2. Análisis de Tendencias por Trimestre y Dirección (explicando el comportamiento de ejecución a lo largo de Q1 a Q4).
     3. Hallazgos de Anomalías Críticas (detallando con sus IDs exactos los casos de sobrecosto mayor al 45% y los retrasos mayores a 90 días).
     4. Dictamen Técnico y Medidas Correctivas (3 acciones concretas de control presupuestal y operativo).
     ```
   * Verifica que el documento se abra en el panel lateral derecho de **Canvas**.

4. **Edición colaborativa e iterativa por secciones dentro de Canvas:**
   * Trabaja directamente sobre el panel derecho de **Canvas** realizando las siguientes 3 iteraciones de mejora puntual:
     * **Iteración 1 (Edición puntual con el ratón):** Selecciona con el cursor únicamente la **Sección 3 (Hallazgos de Anomalías Críticas)** dentro de Canvas, haz clic en el botón flotante **Preguntar a ChatGPT** y escribe: *"Convierte los hallazgos de esta sección en una tabla técnica estructurada con columnas para ID, Tipo de Anomalía, Magnitud del Impacto y Nivel de Riesgo"*.
     * **Iteración 2 (Ajuste de longitud y tono):** En el menú de accesos rápidos de la esquina inferior derecha de Canvas (icono de lápiz/ajustes), selecciona la opción **Ajustar longitud** o escribe en el chat principal: *"En el documento de Canvas, expande la Sección 4 agregando un responsable institucional y un plazo en días para cada una de las 3 medidas correctivas"*.
     * **Iteración 3 (Revisión final de calidad):** Pide en el chat: *"Revisa todo el documento en Canvas para asegurar un tono institucional formal de la DPCI, verifica que todas las cifras coincidan exactamente con el CSV analizado y agrega al final un bloque de firmas para el Líder de Ciencia de Datos y el Director de la DPCI"*.

5. **Exportación y cierre del entregable oficial:**
   * En la esquina superior derecha de la ventana de **Canvas**, utiliza el botón **Copiar** (o **Exportar** según disponibilidad de tu cuenta) para extraer el documento definitivo ya depurado y pégalo en un documento en blanco para su entrega oficial.

## Resultado esperado
Una base de datos masiva autogenerada (`Base_Masiva_DPCI_2026.csv`), su auditoría estadística completa y gráfica de tendencias generadas mediante **Advanced Data Analysis** (Python), y el **Informe Oficial de Conclusiones Técnicas de la DPCI** redactado y refinado de manera iterativa en la interfaz colaborativa **Canvas** de **ChatGPT**.
