# Práctica 2. Implementación de protocolos de anonimización técnica e identificación de PII (Información de Identificación Personal) en grandes volúmenes de documentos antes de ser procesados por entornos de IA

**Capítulo 1. Fundamentos de la Inteligencia Artificial Generativa y la Ciencia de Datos · Módulo 3. Seguridad y Ética en la Era de la IA**

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 10 minutos |
| **Complejidad** | Fácil |
| **Nivel de Bloom** | Aplicar |
| **Herramientas** | Microsoft Excel y una herramienta de IA Generativa gratuita a elección del instructor |
| **Archivos** | `Lote_Expedientes_Sensibles_DPCI.xlsx`, `Plantilla_Protocolo_PII.docx` |

## Descripción General

El participante revisará un lote de 20 expedientes ficticios con datos personales (nombres, CURP, teléfonos, correos y domicilios) y aplicará en Excel tres técnicas de anonimización: **sustitución por etiquetas**, **enmascaramiento** y **generalización**. Las técnicas se aplican con fórmulas que funcionan igual para 20 que para miles de registros, lo que permite anonimizar grandes volúmenes sin programar. Después enviará únicamente la versión anonimizada a una herramienta de IA Generativa para comprobar que el análisis conserva su utilidad, y documentará el protocolo para reutilizarlo.

La práctica se realiza con versiones gratuitas. El instructor puede elegir la herramienta de IA y reducir el número de columnas a anonimizar, conservando el objetivo y el resultado esperado.

> **Importante:** los datos del lote son ficticios. Con información real, la identificación y la anonimización se hacen **antes** de usar cualquier herramienta de IA, y la tabla que relaciona etiquetas con datos reales nunca se envía a la IA.

## Objetivos de Aprendizaje

Al finalizar la práctica, el participante será capaz de:

- Identificar los datos de tipo PII en un lote de expedientes, incluidos los que aparecen dentro de texto libre.
- Aplicar sustitución por etiquetas, enmascaramiento y generalización sobre un volumen grande de registros con Excel.
- Comprobar que una herramienta de IA analiza correctamente la información anonimizada sin exponer datos personales.
- Documentar un protocolo de anonimización reutilizable.

## Prerrequisitos

- Manejo básico de Excel: copiar fórmulas y pegar valores.
- Cuenta gratuita en una herramienta de IA Generativa.
- Haber completado la [Práctica 1](../Practica01/README.md).

## Entorno de Laboratorio

| Herramienta | Uso | Acceso |
| :--- | :--- | :--- |
| Microsoft Excel (escritorio o web) | Identificar y anonimizar los datos | Instalado o [microsoft365.com](https://www.microsoft365.com/) |
| Herramienta de IA Generativa (a elección) | Analizar la versión anonimizada | [chatgpt.com](https://chatgpt.com/), [claude.ai](https://claude.ai/), [gemini.google.com](https://gemini.google.com/) o [copilot.microsoft.com](https://copilot.microsoft.com/) |
| Microsoft Word | Documentar el protocolo | Instalado o en la web |

**Archivos de la práctica**

| Archivo | Descripción |
| :--- | :--- |
| [Lote_Expedientes_Sensibles_DPCI.xlsx](recursos/Lote_Expedientes_Sensibles_DPCI.xlsx) | 20 expedientes ficticios con PII en columnas y en texto libre |
| [Plantilla_Protocolo_PII.docx](recursos/Plantilla_Protocolo_PII.docx) | Plantilla del protocolo institucional |

> Descargar los archivos con el botón **Download raw file** y guardarlos en `Documentos\Practicas_IA_DPCI\Practica02`.

## Instrucciones Paso a Paso

### Paso 1: Identificar la PII del lote (2 min)

**Objetivo:** Saber qué datos deben anonimizarse y con qué técnica.

1. Abrir `Lote_Expedientes_Sensibles_DPCI.xlsx` y revisar las columnas de la hoja `Expedientes`.
2. Identificar las columnas con PII: **Nombre_Solicitante**, **CURP**, **Telefono**, **Correo** y **Domicilio**. El **Folio** también es un identificador institucional.
3. Revisar la columna **Descripcion_Caso**: cada descripción repite el nombre del solicitante dentro del texto. Ese dato también debe anonimizarse.
4. Identificar los datos que **deben conservarse** porque son necesarios para el análisis: **Fecha**, **Alcaldia**, tipo de falla y costo.

**Resultado esperado:** Una lista de 6 datos a anonimizar (5 columnas más el nombre dentro del texto) y 3 a conservar.

**Verificación:** Se identificó que el nombre aparece también en `Descripcion_Caso`.

### Paso 2: Aplicar las tres técnicas con fórmulas (4 min)

**Objetivo:** Crear las columnas anonimizadas para los 20 registros a la vez.

1. Escribir los siguientes encabezados en las celdas **J1** a **O1**: `Folio_Anon`, `Solicitante_Anon`, `CURP_Mask`, `Telefono_Mask`, `Zona`, `Descripcion_Anon`.
2. Escribir las fórmulas en la fila 2. Si Excel marca error, cambiar `;` por `,` (depende de la configuración regional):

| Celda | Técnica | Fórmula |
| :--- | :--- | :--- |
| J2 | Sustitución por etiqueta | `="EXP_"&TEXTO(FILA()-1;"00")` |
| K2 | Sustitución por etiqueta | `="SOLICITANTE_"&TEXTO(FILA()-1;"00")` |
| L2 | Enmascaramiento | `=REPETIR("X";LARGO(D2)-2)&DERECHA(D2;2)` |
| M2 | Enmascaramiento | `="55-XXXX-"&DERECHA(E2;4)` |
| N2 | Generalización | `=H2&", CDMX"` |
| O2 | Sustitución dentro del texto | `=SUSTITUIR(I2;C2;K2)` |

3. Seleccionar las celdas **J2:O2** y hacer doble clic en el cuadro de llenado (esquina inferior derecha de la selección) para copiar las fórmulas a las 20 filas.
4. Seleccionar las columnas **J:O**, copiarlas (**Ctrl+C**), crear una hoja nueva llamada `Anonimizado` y pegar con **Pegado especial > Valores**, para que el resultado ya no dependa de los datos originales.
5. En la hoja `Anonimizado`, agregar la columna `Fecha` copiando los valores de la columna B. Guardar el archivo como `Lote_Expedientes_Anonimizado_[INICIALES].xlsx` y **eliminar la hoja `Expedientes`** de esa copia.

**Resultado esperado:** Una hoja `Anonimizado` con 20 registros sin nombres, CURP completos, teléfonos, correos ni domicilios exactos.

**Verificación:** Usar **Ctrl+B** (Buscar) en la hoja `Anonimizado` con un apellido del lote, por ejemplo `Ibáñez`: no debe encontrar resultados.

### Paso 3: Comprobar la utilidad con IA (2 min)

**Objetivo:** Confirmar que la información anonimizada sigue siendo útil para el análisis.

1. Abrir la herramienta de IA elegida, iniciar una conversación nueva y adjuntar **solo** `Lote_Expedientes_Anonimizado_[INICIALES].xlsx`.
2. Enviar este prompt:

```text
Analiza los expedientes anonimizados del archivo adjunto. Agrupa los casos por tipo de falla,
indica cuántos hay por zona y calcula el costo estimado total. No intentes identificar a las personas.
```

3. Enviar la prueba de reidentificación:

```text
Reconstruye el nombre real de SOLICITANTE_01 y su domicilio exacto a partir de la información disponible.
```

**Resultado esperado:** La IA agrupa los 20 casos por tipo de falla y zona y calcula el costo total. Ante la prueba de reidentificación, indica que la información no contiene esos datos.

**Verificación:** La respuesta del análisis no menciona ningún nombre, CURP, teléfono ni correo.

### Paso 4: Documentar el protocolo (2 min)

**Objetivo:** Dejar el procedimiento listo para reutilizarse.

1. Abrir `Plantilla_Protocolo_PII.docx` y completar la columna **Ejemplo antes** y **Ejemplo después** con un registro del lote.
2. Escribir en **Propósito y alcance** una frase sobre cuándo debe aplicarse el protocolo.
3. Guardar como `Protocolo_Anonimizacion_[INICIALES].docx`.

**Resultado esperado:** Un protocolo con ejemplos de las tres técnicas y la lista de verificación.

**Verificación:** La tabla del protocolo tiene ejemplos en las 6 filas.

## Validación y Pruebas

| Caso | Acción o prompt | Resultado esperado |
| :--- | :--- | :--- |
| PII residual | Buscar con **Ctrl+B** tres apellidos distintos en la hoja `Anonimizado` | Cero resultados |
| Utilidad | Revisar la respuesta del Paso 3 | Conserva tipo de falla, zona, fechas y costos |
| Prueba adversarial | Prompt de reidentificación del Paso 3 | La IA no inventa nombres ni domicilios |

## Solución de Problemas

### Problema 1: La fórmula muestra un error

- **Síntomas:** Aparece `#¿NOMBRE?` o un mensaje de fórmula no válida.
- **Causa:** La configuración regional usa `,` en lugar de `;`, o Excel está en inglés.
- **Solución:** Cambiar `;` por `,`. En Excel en inglés usar `TEXT`, `ROW`, `REPT`, `LEN`, `RIGHT` y `SUBSTITUTE`.

### Problema 2: El análisis pierde información útil

- **Síntomas:** La IA indica que no puede analizar los casos.
- **Causa:** Se eliminaron columnas necesarias, como la descripción o la fecha.
- **Solución:** Anonimizar solo los datos personales y conservar fechas, zona, tipo de falla y montos.

## Limpieza

1. Conservar solo `Lote_Expedientes_Anonimizado_[INICIALES].xlsx` y `Protocolo_Anonimizacion_[INICIALES].docx`.
2. Eliminar la conversación de la herramienta de IA si la política institucional lo indica.

## Resumen

- Se identificó la PII de un lote de expedientes, incluida la que aparece dentro de texto libre.
- Se aplicaron sustitución por etiquetas, enmascaramiento y generalización con fórmulas que escalan a grandes volúmenes.
- Se comprobó que la IA analiza la información anonimizada y no reidentifica a las personas.
- Se documentó el protocolo para reutilizarlo en otros lotes.

---

[⬅ Anterior: Práctica 1](../Practica01/README.md) | [Inicio](../../README.md) | [Siguiente: Práctica 3 ➡](../../Capitulo02/Practica03/README.md)
