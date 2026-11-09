# Práctica 1. Implementar un proceso de verificación cruzada para validar la información generada por IA e identificar posibles inconsistencias antes de incorporarla a documentos institucionales

**Capítulo 1. Fundamentos de la Inteligencia Artificial Generativa y la Ciencia de Datos · Módulo 3. Seguridad y Ética en la Era de la IA**

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 10 minutos |
| **Complejidad** | Fácil |
| **Nivel de Bloom** | Aplicar |
| **Herramientas** | Dos herramientas de IA Generativa gratuitas, a elección del instructor (por ejemplo ChatGPT, Microsoft Copilot, Gemini o Claude), Microsoft Word y Microsoft Excel |
| **Archivos** | `Reporte_Auditoria_DPCI_2024.docx`, `Matriz_Verificacion_Cruzada.xlsx` |

## Descripción General

Antes de incorporar a un documento institucional un resumen generado por IA, la DPCI exige verificarlo. En esta práctica el participante pedirá a dos herramientas de IA Generativa el mismo resumen de un reporte de auditoría ficticio y contrastará cada afirmación relevante contra el documento original y contra la otra herramienta. Registrará en una matriz los datos confirmados, las imprecisiones, las posibles alucinaciones y los sesgos, junto con la corrección necesaria.

La práctica se realiza con versiones gratuitas. El instructor puede elegir las herramientas según su disponibilidad y límites de consumo, y ajustar la cantidad de afirmaciones a verificar, conservando el objetivo y el resultado esperado.

## Objetivos de Aprendizaje

Al finalizar la práctica, el participante será capaz de:

- Aplicar un proceso de verificación cruzada comparando dos herramientas de IA Generativa contra una fuente original.
- Identificar imprecisiones, alucinaciones y sesgos en un resumen generado por IA.
- Registrar los resultados en una matriz de verificación con estado y corrección requerida.

## Prerrequisitos

- Manejo básico de Word y Excel.
- Cuenta gratuita en al menos dos herramientas de IA Generativa (ver [Setup_Guide.md](../../Setup_Guide.md)).
- Haber revisado los conceptos de alucinación y sesgo del Módulo 3.

## Entorno de Laboratorio

| Herramienta | Uso | Acceso |
| :--- | :--- | :--- |
| Herramienta de IA "A" (por ejemplo ChatGPT) | Generar el primer resumen | [chatgpt.com](https://chatgpt.com/) |
| Herramienta de IA "B" (por ejemplo Claude, Gemini o Copilot) | Generar el segundo resumen | [claude.ai](https://claude.ai/), [gemini.google.com](https://gemini.google.com/), [copilot.microsoft.com](https://copilot.microsoft.com/) |
| Microsoft Word y Excel (escritorio o web) | Leer el reporte y llenar la matriz | Instalados en el equipo o [microsoft365.com](https://www.microsoft365.com/) |

**Archivos de la práctica**

| Archivo | Descripción |
| :--- | :--- |
| [Reporte_Auditoria_DPCI_2024.docx](recursos/Reporte_Auditoria_DPCI_2024.docx) | Reporte de auditoría ficticio con 5 hallazgos (fuente original) |
| [Matriz_Verificacion_Cruzada.xlsx](recursos/Matriz_Verificacion_Cruzada.xlsx) | Matriz con 8 afirmaciones a verificar y la hoja `Estados` con su significado |

> **Cómo descargar los archivos:** hacer clic en el nombre del archivo y, en la página que se abre, seleccionar el botón **Download raw file** (icono de descarga, arriba a la derecha). Guardar los archivos en la carpeta `Documentos\Practicas_IA_DPCI\Practica01`.

## Instrucciones Paso a Paso

### Paso 1: Preparar la fuente y la matriz (2 min)

**Objetivo:** Tener a la mano la fuente original y saber qué afirmaciones se van a verificar.

1. Abrir `Reporte_Auditoria_DPCI_2024.docx` en Word y leer las secciones **Resumen ejecutivo** y **Hallazgos principales**.
2. Abrir `Matriz_Verificacion_Cruzada.xlsx` en Excel. Revisar la hoja `Estados` para conocer los cuatro estados posibles: **CONFIRMADO**, **IMPRECISIÓN**, **ALUCINACIÓN** y **SESGO**.
3. En la hoja `Matriz`, llenar la columna **Dato_en_fuente_original** de las 8 filas con el dato exacto del reporte. Por ejemplo, fila 1: *145 servidores*; fila 3: *4.2 h frente a SLA de 2.0 h*.

**Resultado esperado:** La columna `Dato_en_fuente_original` tiene los 8 datos exactos del reporte.

**Verificación:** La fila 4 indica *Artículo 14 del Reglamento Interno de Ciberseguridad* y la fila 7 indica *5 días hábiles*.

### Paso 2: Obtener el resumen con la Herramienta A (2 min)

**Objetivo:** Generar el primer resumen con una instrucción que limite la respuesta a la fuente.

1. Abrir la Herramienta A en el navegador e iniciar sesión.
2. Iniciar una conversación nueva, adjuntar `Reporte_Auditoria_DPCI_2024.docx` con el botón de adjuntar (clip o **+**) y enviar este prompt:

```text
Actúa como auditor técnico de la DPCI. Con base únicamente en el documento adjunto, entrega:
1) Un resumen ejecutivo de máximo 3 oraciones.
2) Los 5 hallazgos con su código, el dato cuantitativo exacto y la norma citada, si existe.
3) El presupuesto ejercido y el porcentaje de ahorro.
4) El plazo de remediación solicitado.
No agregues datos, normas ni plazos que no estén escritos en el documento.
```

3. Si la herramienta no permite adjuntar archivos, copiar el texto del reporte y pegarlo al final del prompt.

**Resultado esperado:** Un resumen con los hallazgos H-01 a H-05 y sus cifras.

**Verificación:** La respuesta menciona los 5 códigos de hallazgo.

### Paso 3: Obtener el resumen con la Herramienta B (2 min)

**Objetivo:** Obtener un resumen independiente con la misma instrucción para compararlo.

1. Abrir la Herramienta B en otra pestaña, iniciar una conversación nueva y repetir el Paso 2 con el mismo archivo y el mismo prompt.

**Resultado esperado:** Un segundo resumen independiente.

**Verificación:** Ambas respuestas están abiertas en pestañas distintas para compararlas.

### Paso 4: Llenar la matriz de verificación (4 min)

**Objetivo:** Clasificar cada afirmación según su coincidencia con la fuente.

1. Para cada una de las 8 filas, copiar en **Respuesta_Herramienta_A** y **Respuesta_Herramienta_B** lo que dijo cada herramienta sobre esa afirmación.
2. En la columna **Estado**, asignar uno de los cuatro estados de la hoja `Estados`:
   - **CONFIRMADO** si ambas coinciden con la fuente.
   - **IMPRECISIÓN** si redondean o mezclan datos (por ejemplo, confunden el presupuesto asignado de 51,364 USD con el ejercido de 45,200 USD).
   - **ALUCINACIÓN** si agregan una norma, plazo o dato que no está en el reporte (por ejemplo, citar ISO 27001).
   - **SESGO** si usan adjetivos que la fuente no contiene (por ejemplo, "falla catastrófica").
3. En **Correccion_requerida**, escribir la redacción correcta tomada de la fuente cuando el estado no sea CONFIRMADO.
4. Guardar el archivo como `Matriz_Verificacion_Cruzada_[INICIALES].xlsx`.

**Resultado esperado:** Una matriz con las 8 afirmaciones evaluadas y la corrección de cada discrepancia.

**Verificación:** Ninguna fila de la columna `Estado` queda vacía, y toda fila distinta de CONFIRMADO tiene una corrección.

## Validación y Pruebas

| Caso | Acción o prompt | Resultado esperado |
| :--- | :--- | :--- |
| Cifra exacta | Comparar la fila 3 con la fuente | 4.2 h y SLA de 2.0 h coinciden; estado CONFIRMADO o IMPRECISIÓN si alguna herramienta redondea |
| Norma citada | Revisar la fila 4 | Solo debe aparecer el Artículo 14; cualquier otra norma es ALUCINACIÓN |
| Prueba adversarial | Preguntar a la Herramienta A: *"¿Qué sanción establece la norma ISO 27001 para el hallazgo H-02?"* | La herramienta debe indicar que el documento no menciona ISO 27001. Si inventa una sanción, registrarlo como ALUCINACIÓN |

## Solución de Problemas

### Problema 1: La herramienta cita normas que no están en el reporte

- **Síntomas:** Aparecen referencias a ISO 27001, NIST u otras normas.
- **Causa:** El modelo complementa con su conocimiento general.
- **Solución:** Agregar al prompt: *"Si una norma no está citada en el documento, escribe NO ESPECIFICADO EN EL DOCUMENTO"* y repetir.

### Problema 2: Se alcanza el límite de mensajes de la versión gratuita

- **Síntomas:** La herramienta indica que se alcanzó el límite de uso.
- **Causa:** Restricciones de la versión gratuita.
- **Solución:** Usar otra herramienta de la lista para el resumen faltante; el ejercicio solo requiere dos herramientas distintas.

## Limpieza

1. Conservar `Matriz_Verificacion_Cruzada_[INICIALES].xlsx` en `Documentos\Practicas_IA_DPCI\Practica01`.
2. Si la política institucional lo indica, eliminar las conversaciones de ambas herramientas desde su historial.

## Resumen

- Se generaron dos resúmenes independientes de un mismo documento con herramientas distintas.
- Se contrastaron 8 afirmaciones contra la fuente original y entre herramientas.
- Se registraron imprecisiones, alucinaciones y sesgos con su corrección, como paso previo obligatorio antes de usar contenido generado por IA en un documento institucional.

---

[Inicio](../../README.md) | [Siguiente: Práctica 2 ➡](../Practica02/README.md)
