# Práctica 2. Implementación de protocolos de anonimización técnica e identificación de PII (Información de Identificación Personal) en grandes volúmenes de documentos antes de ser procesados por entornos de IA

**Duración de la práctica:** 30 min

## Descripción
Los participantes aplicarán protocolos técnicos de identificación, clasificación y anonimización de Información de Identificación Personal (PII) y datos sensibles de la DPCI antes de someter grandes volúmenes de documentos a entornos externos de Inteligencia Artificial Generativa. Mediante datos y expedientes sintéticos 100% autogenerados, los asistentes aprenderán a detectar datos personales directos e indirectos, aplicar técnicas de enmascaramiento y seudonimización estructurada, y ejecutar auditorías de fugas de privacidad cruzando **ChatGPT** y **Claude**, sin requerir archivos externos.

---

## Sección 1: Demostración del Instructor (3 Pasos)

1. **Generación de un expediente institucional con PII sensible en ChatGPT:**
   * El instructor abre **ChatGPT** y envía el siguiente prompt para simular un registro administrativo con datos personales mezclados:
     ```text
     Actúa como un Coordinador Administrativo de la DPCI.
     
     Genera un reporte ficticio de atención ciudadana y gestión contractual de 250 palabras que incluya explícitamente:
     - Nombres completos de 2 ciudadanos y 1 funcionario público.
     - Números de documento de identidad, correos electrónicos personales, teléfonos celulares y direcciones físicas.
     - 1 número de cuenta bancaria para desembolso y 1 diagnóstico médico breve asociado a una solicitud de incapacidad.
     
     Aclara en el encabezado que son datos 100% sintéticos de prueba.
     ```

2. **Detección y mapeo de entidades PII en ChatGPT:**
   * En la misma sesión de **ChatGPT**, el instructor solicita identificar y catalogar cada dato sensible antes de transformarlo:
     ```text
     Analiza el reporte anterior y extrae en una tabla Markdown todos los elementos de Información de Identificación Personal (PII) y datos sensibles detectados.
     
     Columnas requeridas: Dato_Detectado, Categoria_PII (Identificador_Directo / Contacto / Financiero / Salud_Sensible), Nivel_Riesgo_Privacidad (Critico / Alto / Medio) y Token_Reemplazo_Propuesto.
     ```

3. **Ejecución de anonimización y auditoría de fuga en Claude:**
   * El instructor abre **Claude**, pega el reporte original del Paso 1 y ejecuta el prompt de sanitización técnica:
     ```text
     Actúa como un Oficial de Protección de Datos (DPO) y Seguridad de la Información de la DPCI.
     
     Aplica un protocolo de anonimización técnica (seudonimización por tokens estructurados como [CIUDADANO_01], [ID_01], [CUENTA_01], [DATO_MEDICO_RESERVADO]) al siguiente documento. 
     
     Regla estricta: Conserva intacta la utilidad analítica y narrativa del caso para que pueda ser procesado por una IA externa sin comprometer la identidad de las personas ni permitir la reidentificación indirecta.
     ```

---

## Sección 2: Práctica Guiada del Participante (30 min)

1. **Autogeneración de un lote masivo de registros con PII y cuasi-identificadores en ChatGPT:**
   * Abre **ChatGPT** y envía el siguiente prompt para generar un conjunto complejo de expedientes no estructurados que simulen un volumen documental real de la DPCI:
     ```text
     Actúa como un Gestor Documental de la DPCI.
     
     Genera un lote ficticio compuesto por 4 expedientes cortos (de unas 120 palabras cada uno) sobre trámites internos, quejas ciudadanas y contratación de servicios. 
     
     Cada expediente debe contener mezclados en su redacción:
     - Nombres completos, números de identificación nacional y números de pasaporte o licencia.
     - Correos electrónicos institucionales y personales, números telefónicos y direcciones residenciales exactas.
     - Datos financieros (números de tarjeta, cuentas bancarias o salarios exactos).
     - Cuasi-identificadores indirectos (por ejemplo: cargo único en una oficina pequeña, fecha exacta de nacimiento y ciudad de residencia que permitirían deducir quién es la persona).
     
     Usa datos 100% inventados y sepáralos como EXPEDIENTE 1, EXPEDIENTE 2, EXPEDIENTE 3 y EXPEDIENTE 4.
     ```
   * Copia y guarda los 4 expedientes generados en un bloc de notas temporal como tu **Lote Documental Crudo**.

2. **Construcción de la matriz de inventario PII y diccionario de seudonimización en ChatGPT:**
   * En el mismo chat de **ChatGPT**, envía el siguiente prompt para estructurar el protocolo de catalogación previo al enmascaramiento:
     ```text
     Actúa como un Especialista en Ciberseguridad y Gobernanza de Datos de la DPCI.
     
     Audita los 4 expedientes anteriores y construye un Diccionario de Anonimización en tabla Markdown con las siguientes columnas:
     - Expediente_Origen (1 a 4)
     - Valor_Original_Detectado
     - Tipo_Informacion (PII_Directa / PII_Financiera / Dato_Sensible / Cuasi_Identificador)
     - Riesgo_Reidentificacion (Alto / Medio / Bajo)
     - Etiqueta_Token_Sustitucion (ejemplo: [SUJETO_A], [DOC_ID_01], [DIR_01], [SALARIO_RANGO])
     
     Asegúrate de no omitir ningún dato de contacto, número o referencia indirecta.
     ```

3. **Ejecución del protocolo de sanitización y enmascaramiento profundo en Claude:**
   * Abre **Claude** en una nueva ventana del navegador.
   * Copia el **Lote Documental Crudo** (los 4 expedientes generados en el Paso 1) y pégalo debajo del siguiente prompt:
     ```text
     Actúa como un Ingeniero de Privacidad de Datos de la DPCI.
     
     Tu tarea es sanitizar el siguiente lote de 4 expedientes para que puedan ser ingresados de forma segura a un modelo público de Inteligencia Artificial para análisis estadístico.
     
     Aplica estas reglas técnicas obligatorias:
     1. Reemplaza todos los nombres, documentos, teléfonos, correos, direcciones y cuentas bancarias por etiquetas estandarizadas entre corchetes (ejemplo: [PERSONA_01], [ID_01], [CORREO_01], [CUENTA_01]).
     2. Generaliza los cuasi-identificadores (convierte fechas de nacimiento exactas en rangos de edad, salarios exactos en rangos salariales y direcciones en solo región o zona).
     3. Mantén intactos los hechos administrativos, fechas de trámite, montos globales del proyecto y problemas operativos para no perder valor analítico.
     
     Entrega únicamente los 4 expedientes ya anonimizados.
     ```

4. **Auditoría cruzada de fugas de privacidad (Red Teaming de Reidentificación) en Claude:**
   * En la misma conversación de **Claude**, envía el siguiente prompt para poner a prueba la calidad de la anonimización y verificar que no hayan quedado brechas:
     ```text
     Actúa como un Auditor de Seguridad y Atacante Ético (Red Team de Privacidad).
     
     Revisa minuciosamente los 4 expedientes anonimizados que acabas de generar y responde:
     1. ¿Quedó algún dato personal directo, número, correo o nombre real sin enmascarar?
     2. ¿Es posible deducir la identidad de alguna persona cruzando los cuasi-identificadores restantes (cargo, ubicación, contexto)? Si es así, indica exactamente qué frase debe generalizarse aún más.
     3. Emite un Dictamen de Cumplimiento en una tabla corta indicando por cada expediente: Estado (APROBADO PARA IA EXTERNA / REQUIERE AJUSTE) y Justificación Técnica.
     ```

5. **Validación de utilidad analítica con datos ya anonimizados en ChatGPT:**
   * Regresa a **ChatGPT** (en una conversación limpia/nueva), copia y pega los **4 expedientes ya anonimizados y aprobados en Claude**, y envía el siguiente prompt para comprobar que el documento mantiene su valor operativo para la DPCI:
     ```text
     Actúa como un Analista de Inteligencia de Datos de la DPCI.
     
     Analiza el siguiente lote de 4 expedientes previamente anonimizados y genera:
     1. Un resumen ejecutivo con los principales patrones operativos, cuellos de botella y riesgos institucionales detectados en los 4 casos.
     2. Una tabla de clasificación por tipo de trámite, prioridad de atención y área responsable.
     3. Confirma explícitamente al final si pudiste realizar el análisis completo sin necesidad de conocer la identidad real de los ciudadanos o funcionarios involucrados.
     ```

## Resultado esperado
Un **Diccionario de Anonimización PII** estructurado en **ChatGPT**, un **Lote de 4 Expedientes Sanitizados y Auditados** en **Claude** libre de fuga de datos directos o cuasi-identificadores, y un **Informe Analítico Operativo** generado sobre los datos protegidos que demuestra la viabilidad del análisis sin comprometer la privacidad institucional.
