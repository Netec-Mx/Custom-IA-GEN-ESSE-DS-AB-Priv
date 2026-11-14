# Práctica 6. Prueba de rendimiento comparativa sometiendo a las distintas herramientas al análisis conjunto de un informe técnico extenso y su material visual asociado (gráficas o diagramas), evaluando su capacidad multimodal

**Duración de la práctica:** 30 min

## Descripción
Los participantes someterán simultáneamente las cuatro plataformas principales de Inteligencia Artificial Generativa (**ChatGPT**, **Microsoft Copilot**, **Google Gemini** y **Claude**) a una prueba de rendimiento comparativa (*Benchmark* multimodal) para analizar de forma conjunta un informe técnico extenso de la DPCI y su material visual asociado (diagramas de arquitectura y gráficas financieras). Mediante material 100% autogenerado, cada paso dependerá de los insumos creados previamente para evaluar la precisión en lectura de imágenes, el cruce de datos entre texto y gráficos, la detección de inconsistencias visuales y la calidad de síntesis ejecutiva de cada modelo.

---

## Sección 1: Demostración del Instructor (3 Pasos)

1. **Autogeneración del informe técnico y del material visual en ChatGPT:**
   * El instructor abre **ChatGPT** y envía el siguiente prompt para crear tanto el texto técnico como una gráfica financiera descargable que servirá como insumo multimodal:
     ```text
     Actúa como un Arquitecto de Proyectos de la DPCI.
     
     1. Redacta un breve Informe Técnico (250 palabras) sobre el "Despliegue de Nube Híbrida DPCI" indicando un presupuesto total de $500.000 USD y una meta de disponibilidad del 99.9%.
     2. Genera y entrega como imagen PNG descargable un gráfico de barras titulado "Distribución Presupuestal DPCI" con estos valores exactos: Servidores ($220.000), Seguridad ($180.000) y Capacitación ($150.000). (Nota: introduce intencionalmente esa suma de $550.000 en el gráfico para que no coincida con los $500.000 del texto).
     ```
   * El instructor descarga la imagen PNG generada y copia el texto técnico.

2. **Prueba de lectura multimodal y detección de discrepancias en Google Gemini y Claude:**
   * El instructor abre **Google Gemini** y **Claude** en pestañas paralelas, adjunta la imagen PNG descargada, pega el texto técnico del Paso 1 y ejecuta en ambas plataformas el mismo prompt de evaluación:
     ```text
     Actúa como un Auditor Técnico Multimodal de la DPCI.
     
     Analiza conjuntamente el texto del informe técnico y la imagen gráfica adjunta. Extrae los valores de cada barra del gráfico, súmalos y responde: ¿Existe alguna contradicción numérica entre lo que afirma el texto y lo que muestra la imagen?
     ```

3. **Contraste de rendimiento en Microsoft Copilot y matriz de veredicto:**
   * El instructor repite la misma carga de imagen y texto en **Microsoft Copilot** y compara en pantalla las tres respuestas obtenidas (Gemini, Claude y Copilot), evaluando cuál identificó con mayor exactitud la discrepancia de $50.000 USD entre el texto y el gráfico.

---

## Sección 2: Práctica Guiada del Participante (30 min)

1. **Autogeneración del paquete multimodal (Informe Técnico + Gráfica + Diagrama) en ChatGPT:**
   * Abre **ChatGPT** y envía el siguiente prompt para generar el expediente técnico completo y dos piezas visuales descargables (una gráfica de datos y un diagrama de flujo operacional) con inconsistencias ocultas para poner a prueba a las demás IAs:
     ```text
     Actúa como un Director Técnico de Infraestructura y Datos de la DPCI.
     
     Construye un paquete de prueba multimodal sobre el proyecto "Modernización de Centros de Atención Regional DPCI":
     
     PARTE 1 (Texto Técnico - 350 palabras):
     Redacta el informe técnico oficial especificando:
     - Presupuesto total aprobado: $900.000 USD.
     - 3 fases de ejecución: Fase 1 (Diagnóstico - 2 meses), Fase 2 (Implementación - 4 meses) y Fase 3 (Cierre y Auditoría - 2 meses). Duración total: 8 meses.
     - Meta de reducción de tiempos de atención: 40%.
     
     PARTE 2 (Material Visual 1 - Imagen PNG descargable):
     Genera un gráfico de barras de alta resolución titulado "Inversión por Componente DPCI" con 3 barras exactas: Hardware ($400.000), Software ($350.000) y Redes ($200.000). (Nota: la suma da $950.000 USD, creando una discrepancia intencional frente al texto).
     
     PARTE 3 (Material Visual 2 - Imagen PNG descargable):
     Genera un diagrama de flujo visual limpio titulado "Cronograma de Fases DPCI" que muestre las 3 fases conectadas por flechas, pero indica en las cajas: Fase 1 (2 meses), Fase 2 (5 meses) y Fase 3 (2 meses). (Nota: creando una discrepancia de 1 mes adicional frente al texto).
     ```
   * Copia el texto técnico de la Parte 1 y descarga ambas imágenes PNG (`Grafico_Inversion_DPCI.png` y `Diagrama_Fases_DPCI.png`). Este paquete será tu **Insumo Único de Evaluación**.

2. **Evaluación multimodal en paralelo: Prueba en Google Gemini:**
   * Abre **Google Gemini**, haz clic en el botón de adjuntar archivos (**+**) y sube las dos imágenes descargadas (`Grafico_Inversion_DPCI.png` y `Diagrama_Fases_DPCI.png`).
   * Pega el **Texto Técnico (Parte 1)** junto con el siguiente prompt estandarizado de auditoría multimodal:
     ```text
     Actúa como un Evaluador Técnico Senior de la DPCI.
     
     Analiza de forma integrada el texto técnico adjunto y las dos imágenes (el gráfico de barras y el diagrama de flujo). Ejecuta exactamente estas 4 tareas:
     1. Extrae todas las cifras del gráfico de barras y calcula su suma total.
     2. Extrae los tiempos de cada bloque del diagrama de flujo y calcula la duración total.
     3. Cruza la información visual contra el texto técnico e identifica TODAS las inconsistencias numéricas o temporales entre ambos formatos.
     4. Redacta un dictamen técnico de máximo 120 palabras explicando el impacto de estas discrepancias para la aprobación del proyecto.
     ```
   * Guarda la respuesta completa de **Google Gemini** etiquetándola como `Resultado_Gemini`.

3. **Evaluación multimodal en paralelo: Prueba en Claude y Microsoft Copilot:**
   * Abre **Claude** en una pestaña y **Microsoft Copilot** en otra pestaña.
   * En **ambas plataformas**, adjunta exactamente las mismas dos imágenes (`Grafico_Inversion_DPCI.png` y `Diagrama_Fases_DPCI.png`), pega el mismo **Texto Técnico (Parte 1)** y envía exactamente el **mismo prompt estandarizado** utilizado en el Paso 2.
   * Guarda las respuestas obtenidas etiquetándolas como `Resultado_Claude` y `Resultado_Copilot`.

4. **Auditoría de calidad y generación de la Matriz de Benchmark en ChatGPT:**
   * Regresa a **ChatGPT** (en una nueva conversación limpia para evitar sesgos de memoria) y pega los tres resultados obtenidos en los pasos anteriores (`Resultado_Gemini`, `Resultado_Claude` y `Resultado_Copilot`) debajo del siguiente prompt de evaluación comparativa:
     ```text
     Actúa como un Especialista en Evaluación de Modelos de Inteligencia Artificial de la DPCI.
     
     A continuación te entrego las respuestas de tres plataformas (Google Gemini, Claude y Microsoft Copilot) al someterlas a una misma prueba multimodal donde existían dos errores ocultos entre el texto y las imágenes:
     - Error Oculto 1: El presupuesto del texto era $900.000 USD, pero la suma de barras del gráfico daba $950.000 USD (diferencia de +$50.000 USD).
     - Error Oculto 2: La duración del texto era 8 meses (Fase 2 = 4 meses), pero el diagrama mostraba 9 meses (Fase 2 = 5 meses).
     
     Evalúa el desempeño de las 3 herramientas (e incluye una autoevaluación de las capacidades de ChatGPT para este tipo de tareas) generando una Matriz Comparativa en tabla Markdown con las columnas:
     - Plataforma_IA (ChatGPT / Gemini / Claude / Copilot)
     - Deteccion_Error_Presupuestal (Si_Exacto / Parcial / No_Detectado)
     - Deteccion_Error_Cronograma (Si_Exacto / Parcial / No_Detectado)
     - Precision_Lectura_OCR_Visual (Alta / Media / Baja)
     - Calidad_Sintesis_Ejecutiva (1 a 10)
     - Caso_Uso_Recomendado_DPCI
     ```

5. **Emisión de la Guía Oficial de Selección de Herramientas de IA para la DPCI:**
   * En la misma sesión de **ChatGPT**, solicita transformar la tabla de resultados del Paso 4 en una recomendación institucional definitiva:
     ```text
     Con base en la Matriz Comparativa del paso anterior, redacta una "Guía Rápida de Selección de Plataformas IA para Profesionales de la DPCI" (máximo 250 palabras) que responda claramente:
     1. ¿Qué herramienta elegir cuando se necesita generar gráficas y procesar archivos complejos?
     2. ¿Qué herramienta elegir para auditoría cruzada de documentos extensos y diagramas?
     3. ¿Qué protocolo obligatorio de verificación visual debe aplicar todo analista de la DPCI antes de confiar en la lectura de gráficos hecha por una IA?
     ```

## Resultado esperado
Un paquete multimodal autogenerado en **ChatGPT** (texto técnico + dos gráficos PNG con discrepancias inducidas), los dictámenes analíticos obtenidos en paralelo en **Google Gemini**, **Claude** y **Microsoft Copilot**, una **Matriz Comparativa de Rendimiento Multimodal** evaluando las 4 plataformas y una **Guía Institucional de Selección de Herramientas IA** para la DPCI.
