# Práctica 4. Diseñar prompts de control para forzar a la IA a auditar bases de datos textuales sin cometer errores de omisión

**Duración de la práctica:** 30 min

## Descripción
Los participantes diseñarán prompts de control estricto (delimitación de alcance, conteo explícito de registros, verificación negativa y extracción exhaustiva) para obligar a la Inteligencia Artificial a auditar bases de datos textuales de la DPCI sin omitir registros, truncar respuestas ni resumir información crítica. Utilizando datos 100% autogenerados y combinando **ChatGPT** y **Microsoft Copilot**, los asistentes aprenderán a neutralizar la tendencia de los modelos a "resumir por pereza" y garantizarán la integridad total de los datos extraídos.

---

## Sección 1: Demostración del Instructor (3 Pasos)

1. **Autogeneración de una base de datos textual densa en ChatGPT:**
   * El instructor abre **ChatGPT** y envía el siguiente prompt para simular un registro continuo de novedades operativas donde suelen ocurrir omisiones al analizar texto:
     ```text
     Actúa como un Coordinador de Seguimiento Operativo de la DPCI.
     
     Genera una base de datos textual continua (sin tablas, solo párrafos numerados del [REG-01] al [REG-08]) sobre incidencias reportadas en oficinas regionales. 
     En exactamente 3 de esos registros (ocúltalos en las posiciones 2, 5 y 7), incluye la palabra clave "CRÍTICO" acompañada de un código de falla y un monto de afectación en USD. Los demás registros deben ser novedades rutinarias sin afectación económica.
     ```

2. **Demostración de fallo común vs. Prompt de control con conteo explícito en ChatGPT:**
   * En la misma sesión de **ChatGPT**, el instructor aplica un prompt de control que obliga al modelo a auditar todos los registros uno por uno antes de filtrar:
     ```text
     Actúa como un Auditor de Integridad de Datos de la DPCI.
     
     Audita la base de datos textual anterior aplicando estas reglas de control estricto contra omisiones:
     1. Verifica primero el total de registros presentes (debe ser exactamente 8).
     2. Evalúa uno por uno desde el [REG-01] hasta el [REG-08] sin saltar ninguno.
     3. Extrae en una tabla Markdown únicamente los registros que contengan la palabra "CRÍTICO", indicando: ID_Registro, Codigo_Falla y Monto_USD.
     4. Al final, escribe una línea de control: "Total registros auditados: X | Total hallazgos críticos extraídos: Y".
     ```

3. **Auditoría de completitud y verificación negativa en Microsoft Copilot:**
   * El instructor abre **Microsoft Copilot**, pega la base de datos del Paso 1 y ejecuta un prompt de control cruzado para validar que ningún registro haya sido excluido por error:
     ```text
     Actúa como un Supervisor de Control Interno de la DPCI.
     
     Revisa los 8 registros textuales adjuntos. Tu tarea es comprobar que no existan omisiones. 
     Lista en dos grupos separados:
     - Grupo A (Con afectación económica): ID y monto exacto.
     - Grupo B (Sin afectación económica): Solo los IDs separados por comas.
     
     Regla de control: La suma de elementos del Grupo A más el Grupo B debe ser exactamente 8. Si no suma 8, detente y corrige tu conteo.
     ```

---

## Sección 2: Práctica Guiada del Participante (30 min)

1. **Autogeneración de una base de datos textual extensa de contratos y expedientes en ChatGPT:**
   * Abre **ChatGPT** y envía el siguiente prompt para crear una base de datos textual no estructurada de 12 registros con condiciones ocultas:
     ```text
     Actúa como un Administrador de Bases Documentales de la DPCI.
     
     Genera una base de datos textual compuesta por 12 registros numerados correlativamente desde [EXP-101] hasta [EXP-112], redactados en formato de bitácora narrativa (un párrafo de 45 palabras por cada registro).
     
     Distribuye dentro de los 12 registros las siguientes condiciones específicas:
     - Exactamente 4 registros (ubicados en las posiciones 102, 105, 109 y 111) deben incluir una alerta de "VENCIMIENTO INMINENTE" junto con una fecha límite y una multa diaria en USD.
     - Exactamente 3 registros (ubicados en las posiciones 103, 107 y 112) deben mencionar "PENDIENTE FIRMA JURÍDICA".
     - Los 5 registros restantes deben indicar estado "EN EJECUCIÓN NORMAL" sin alertas ni multas.
     
     No agrupes los registros por categoría; preséntalos estrictamente en orden secuencial del [EXP-101] al [EXP-112].
     ```
   * Copia y guarda los 12 registros generados en un bloc de notas temporal como tu **Bitácora Textual Base**.

2. **Ejecución de auditoría exhaustiva con checklist de barrido completo en ChatGPT:**
   * En la misma conversación de **ChatGPT**, envía el siguiente prompt diseñado con mecanismos de control de conteo, prohibición de truncamiento y verificación de suma cero:
     ```text
     Actúa como un Auditor Forense de Datos de la DPCI.
     
     Audita la Bitácora Textual Base ([EXP-101] a [EXP-112]) bajo un protocolo de Cero Omisiones. Ejecuta las siguientes instrucciones en orden obligatorio:
     1. Declara explícitamente cuántos registros recibiste en total antes de analizar.
     2. Construye una tabla Markdown de barrido completo que contenga las 12 filas obligatorias (una fila por cada expediente del 101 al 112, prohibido usar "etc." o agrupar filas).
     3. Columnas requeridas: ID_Expediente, Estado_Detectado (VENCIMIENTO_INMINENTE / PENDIENTE_FIRMA / EJECUCION_NORMAL), Fecha_Limite_o_NA, Multa_Diaria_USD_o_Zero y Verificacion_Linea (OK).
     4. Agrega al pie de la tabla una línea de cuadre matemático: "Conteo Total = 12 | Vencimientos = X | Pendientes Firma = Y | Normales = Z (X+Y+Z debe ser igual a 12)".
     ```

3. **Extracción condicionada y prueba de estrés contra omisiones en Microsoft Copilot:**
   * Abre **Microsoft Copilot** en una nueva ventana del navegador.
   * Copia la **Bitácora Textual Base** (los 12 registros del Paso 1) y pégalos debajo del siguiente prompt de extracción selectiva con control de integridad:
     ```text
     Actúa como un Analista de Control Contractual de la DPCI.
     
     Analiza los 12 párrafos adjuntos ([EXP-101] a [EXP-112]). Necesito extraer exclusivamente los expedientes que representen riesgo financiero o legal (aquellos con "VENCIMIENTO INMINENTE" o "PENDIENTE FIRMA JURÍDICA").
     
     Para garantizar que no cometas errores de omisión al filtrar:
     1. Primero lista en una sola línea los IDs de los expedientes descartados por estar "EN EJECUCIÓN NORMAL" y cuenta cuántos son.
     2. Luego, presenta una tabla detallada únicamente con los expedientes de riesgo, incluyendo: ID_Expediente, Tipo_Alerta, Detalle_Multa_o_Requisito y Accion_Inmediata.
     3. Calcula la suma total de multas diarias en USD de todos los expedientes con vencimiento inminente.
     ```

4. **Auditoría cruzada de discrepancias entre resultados de ambos modelos en Microsoft Copilot:**
   * En la misma sesión de **Microsoft Copilot**, pega la tabla de barrido completo generada en **ChatGPT** (Paso 2) y envía el siguiente prompt para auditar si ambos sistemas coincidieron al 100%:
     ```text
     Actúa como un Supervisor de Aseguramiento de Calidad (QA) de la DPCI.
     
     Compara los resultados que acabas de obtener en el paso anterior contra la tabla de barrido completo generada previamente en otra herramienta (adjunta abajo).
     
     Responde en formato de dictamen técnico:
     1. ¿Coincide exactamente el número de expedientes con "VENCIMIENTO INMINENTE" (deben ser 4) y "PENDIENTE FIRMA JURÍDICA" (deben ser 3)?
     2. ¿Coincide la suma total de las multas diarias en USD?
     3. Si detectas alguna omisión, diferencia de conteo o cifra alterada entre ambas salidas, señálala exactamente indicando el ID del expediente afectado. Si todo cuadra al 100%, emite el sello: "AUDITORÍA DE INTEGRIDAD APROBADA - CERO OMISIONES".
     ```

5. **Creación de una plantilla maestra de Prompt de Control reutilizable en ChatGPT:**
   * Regresa a **ChatGPT** y solicita abstraer la lógica aplicada en esta práctica para estandarizarla en los procedimientos internos de la DPCI:
     ```text
     Actúa como un Ingeniero de Prompts Senior de la DPCI.
     
     Con base en las técnicas de control que utilizamos en esta sesión (conteo previo, barrido secuencial obligatorio, prohibición de truncamiento, conteo de descartados y cuadre matemático final), diseña una "Plantilla Maestra de Prompt de Auditoría Sin Omisiones" lista para copiar y pegar por cualquier funcionario de la DPCI.
     
     La plantilla debe incluir espacios entre corchetes como [PEGAR BASE TEXTUAL AQUÍ] y [CRITERIO DE BÚSQUEDA] para que sea 100% reutilizable en futuros análisis documentales.
     ```

## Resultado esperado
Una **Tabla de Barrido Completo (12 de 12 registros)** con cuadre matemático en **ChatGPT**, una **Extracción Selectiva Auditada con Verificación Negativa** en **Microsoft Copilot**, y una **Plantilla Maestra de Prompt de Control** estandarizada para evitar errores de omisión en auditorías textuales de la DPCI.
