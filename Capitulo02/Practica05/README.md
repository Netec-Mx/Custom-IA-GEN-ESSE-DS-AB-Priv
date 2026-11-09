# Práctica 5. Clasificación y categorización masiva de correspondencia, reportes o expedientes de la DPCI para la extracción automática de metadatos e indicadores estratégicos (KPIs)

**Capítulo 2. Ingeniería de Prompts y Multimodalidad · Módulo 5. Análisis de grandes volúmenes de información mediante IA**

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 30 minutos |
| **Complejidad** | Intermedia |
| **Nivel de Bloom** | Aplicar |
| **Herramientas** | Una herramienta de IA Generativa gratuita a elección del instructor y Microsoft Excel |
| **Archivos** | `Lote_Correspondencia_DPCI_30.txt` (o `.docx`), `Lote_Correspondencia_DPCI_15.txt` (versión reducida) |

## Descripción General

El participante cargará a una herramienta de IA Generativa un lote de **30 documentos** de correspondencia ficticia y anonimizada de la DPCI. Definirá un esquema de categorías y metadatos (fecha, remitente, tipo de documento, tema, prioridad y días estimados de atención), solicitará la clasificación de todos los documentos en una tabla y la llevará a Excel. Con tablas dinámicas calculará los KPIs del área y, con apoyo de la IA, identificará patrones, anomalías e inconsistencias del lote.

La práctica se realiza con versiones gratuitas. El instructor puede elegir la herramienta de IA y usar la versión reducida de 15 documentos si la herramienta tiene límites de longitud, conservando el objetivo y el resultado esperado.

## Objetivos de Aprendizaje

Al finalizar la práctica, el participante será capaz de:

- Definir un esquema de categorías y metadatos para clasificar documentos de forma consistente.
- Extraer con IA los metadatos de un lote completo de documentos sin omisiones.
- Calcular KPIs con tablas dinámicas en Excel a partir de la extracción.
- Identificar patrones, anomalías e inconsistencias en el lote con apoyo de la IA.

## Prerrequisitos

- Haber completado las prácticas [3](../Practica03/README.md) y [4](../Practica04/README.md) (estructura de prompts y prompts de control).
- Manejo básico de Excel: tablas y tablas dinámicas.

## Entorno de Laboratorio

| Herramienta | Uso | Acceso |
| :--- | :--- | :--- |
| Herramienta de IA Generativa (a elección) | Clasificar el lote y analizar anomalías | [chatgpt.com](https://chatgpt.com/), [claude.ai](https://claude.ai/), [gemini.google.com](https://gemini.google.com/) o [copilot.microsoft.com](https://copilot.microsoft.com/) |
| Microsoft Excel | Tabla de metadatos y KPIs | Instalado o [microsoft365.com](https://www.microsoft365.com/) |

**Archivos de la práctica**

| Archivo | Descripción |
| :--- | :--- |
| [Lote_Correspondencia_DPCI_30.txt](recursos/Lote_Correspondencia_DPCI_30.txt) | Lote de 30 oficios y memorandos anonimizados (texto) |
| [Lote_Correspondencia_DPCI_30.docx](recursos/Lote_Correspondencia_DPCI_30.docx) | El mismo lote en Word |
| [Lote_Correspondencia_DPCI_15.txt](recursos/Lote_Correspondencia_DPCI_15.txt) | Versión reducida de 15 documentos |

> Descargar los archivos con el botón **Download raw file** y guardarlos en `Documentos\Practicas_IA_DPCI\Practica05`.

## Instrucciones Paso a Paso

### Paso 1: Revisar el lote y el esquema de metadatos (3 min)

**Objetivo:** Conocer el lote y el esquema con el que se clasificará.

1. Abrir `Lote_Correspondencia_DPCI_30.txt` con el Bloc de notas y revisar los primeros tres documentos. Cada uno tiene ID, fecha, remitente, asunto y detalle.
2. Revisar el esquema que se usará:

| Campo | Regla |
| :--- | :--- |
| ID_Documento | Identificador del documento |
| Fecha | Formato AAAA-MM-DD |
| Remitente | Área del remitente (sin el nombre anonimizado) |
| Tipo_Documento | Oficio (OF) o Memorando (MEM) |
| Categoria | Infraestructura y Redes, Seguridad y Control Jurídico, Gestión Administrativa y Financiera, Transparencia y Gobernanza de Datos |
| Prioridad | Crítica, Alta, Media o Baja |
| Dias_Atencion | Crítica 1-2, Alta 3-5, Media 6-10, Baja 11-15 |

**Resultado esperado:** Conocer los 7 campos y sus valores permitidos.

**Verificación:** El lote tiene 30 documentos (el último es `OF-DPCI-2024-0130`).

### Paso 2: Extraer los metadatos con un prompt de control (6 min)

**Objetivo:** Obtener una tabla con los 30 documentos clasificados, sin omisiones.

1. Abrir la herramienta de IA, iniciar una conversación nueva y adjuntar `Lote_Correspondencia_DPCI_30.txt` (o pegar su contenido al final del prompt).
2. Enviar este prompt:

```text
[ROL] Analista de gestión documental de la DPCI.
[TAREA] Extrae los metadatos de los 30 documentos del lote adjunto.
[CAMPOS] ID_Documento | Fecha | Remitente (solo el área) | Tipo_Documento (Oficio o Memorando) |
Categoria (Infraestructura y Redes, Seguridad y Control Jurídico, Gestión Administrativa y Financiera,
Transparencia y Gobernanza de Datos) | Prioridad (Crítica, Alta, Media, Baja) |
Dias_Atencion (Crítica 1-2, Alta 3-5, Media 6-10, Baja 11-15).
[REGLAS] Procesa los 30 documentos en orden, uno por fila, sin resumir ni agrupar.
Copia la fecha exactamente como aparece, aunque parezca incorrecta.
[FORMATO] Una tabla con los 7 campos como encabezados. Después de la tabla, escribe:
Total esperado: 30 | Total procesado: X.
```

3. Revisar que la tabla tenga 30 filas y que el total procesado sea 30. Si faltan filas, pedir: *"Faltan documentos. Entrega de nuevo la tabla completa de los 30."*

**Resultado esperado:** Una tabla de 30 filas con los 7 campos.

**Verificación:** El documento 026 conserva la fecha `2024-04-31` tal como aparece en el lote.

### Paso 3: Llevar la tabla a Excel (5 min)

**Objetivo:** Tener los metadatos en una tabla de Excel lista para analizar.

1. Seleccionar la tabla en la respuesta de la IA (o usar el botón **Copiar**, si la herramienta lo ofrece) y pegarla en la celda **A1** de un libro nuevo de Excel.
   - Si la herramienta ofrece descargar la tabla como archivo de Excel o CSV, también puede descargarse y abrirse directamente.
2. Seleccionar cualquier celda de los datos y presionar **Ctrl+T** para convertirlos en tabla. Marcar **La tabla tiene encabezados**.
3. En **Diseño de tabla > Nombre de la tabla**, escribir `Tabla_Metadatos`.
4. Comprobar que la columna **Dias_Atencion** esté alineada a la derecha (es número). Si está a la izquierda, seleccionarla y usar **Datos > Texto en columnas > Finalizar** para convertirla.

**Resultado esperado:** Una tabla de Excel con 30 filas y 7 columnas.

**Verificación:** La barra de estado muestra **Recuento: 30** al seleccionar la columna ID_Documento (sin el encabezado).

### Paso 4: Calcular los KPIs con tablas dinámicas (8 min)

**Objetivo:** Medir la carga operativa y la urgencia de la correspondencia.

1. Con una celda de la tabla seleccionada, elegir **Insertar > Tabla dinámica > Nueva hoja de cálculo**. Nombrar la hoja `KPIs`.
2. **Tabla dinámica 1, volumen por categoría:** arrastrar **Categoria** a **Filas**, **ID_Documento** a **Valores** (Recuento) y **Dias_Atencion** a **Valores**. Cambiar este último a **Promedio** (clic en el campo > **Configuración de campo de valor > Promedio**).
3. **Tabla dinámica 2, distribución por prioridad:** insertar otra tabla dinámica en la misma hoja, con **Prioridad** en **Filas** e **ID_Documento** en **Valores**. Cambiar a **Mostrar valores como > % del total general**.
4. Escribir en la hoja `KPIs` estos tres indicadores, cada uno con su fórmula (si Excel marca error, cambiar `;` por `,`):

| KPI | Fórmula |
| :--- | :--- |
| Documentos críticos o altos | `=CONTAR.SI(Tabla_Metadatos[Prioridad];"Crítica")+CONTAR.SI(Tabla_Metadatos[Prioridad];"Alta")` |
| % críticos o altos | `=(CONTAR.SI(Tabla_Metadatos[Prioridad];"Crítica")+CONTAR.SI(Tabla_Metadatos[Prioridad];"Alta"))/30` |
| Promedio de días de atención | `=PROMEDIO(Tabla_Metadatos[Dias_Atencion])` |

   Si usa el lote reducido, cambiar `30` por `15` en la segunda fórmula.
5. Insertar un gráfico de columnas a partir de la tabla dinámica 1 (**Analizar tabla dinámica > Gráfico dinámico**).

**Resultado esperado:** Dos tablas dinámicas, tres KPIs y un gráfico. Como la clasificación depende de la IA, los valores pueden variar ligeramente entre participantes. **Infraestructura y Redes** debe ser la categoría con más documentos y el porcentaje de críticos o altos suele estar entre 40 % y 60 %.

**Verificación:** La suma de porcentajes de la tabla dinámica 2 es 100 %.

### Paso 5: Identificar anomalías e inconsistencias con IA (6 min)

**Objetivo:** Detectar patrones y problemas del lote que no se ven en los KPIs.

1. Volver a la conversación de la IA y enviar:

```text
Con base en el lote original y en la tabla que generaste, identifica:
1) Anomalías de datos: IDs duplicados, fechas inválidas, remitentes no identificados.
2) Inconsistencias de contenido: prioridades que contradicen el detalle del documento, plazos irreales y
   asuntos que se repiten sin resolverse.
3) Patrones o cuellos de botella por categoría.
4) Dos recomendaciones para la dirección.
Cita el ID de cada documento que uses como evidencia. Máximo 300 palabras.
```

2. Comparar la respuesta con las 6 anomalías sembradas en el lote:

| Documento | Anomalía |
| :--- | :--- |
| 015 y 021 | El ID `OF-DPCI-2024-0115` está duplicado |
| 026 | Fecha inválida `2024-04-31` (abril tiene 30 días) |
| 009 | Remitente no identificado que solicita planos sin oficio ni firma |
| 012 | Plazo de 24 horas por un juicio de amparo |
| 029 | Pide prioridad Baja para la fibra principal aunque el respaldo sigue saturado al 95 % (ver 010 y 016) |
| 027 | Las 14 observaciones del documento 002 siguen sin solventar |

3. Anotar en la hoja `KPIs` cuántas de las 6 anomalías detectó la IA y cuáles faltaron.

**Resultado esperado:** La IA detecta la mayoría de las anomalías y cita los IDs de evidencia.

**Verificación:** Cada anomalía reportada por la IA incluye el ID del documento.

### Paso 6: Guardar el entregable (2 min)

1. Guardar el libro como `Consolidado_Metadatos_KPIs_[INICIALES].xlsx` en `Documentos\Practicas_IA_DPCI\Practica05`.
2. Pegar en una hoja nueva llamada `Analisis_IA` la respuesta del Paso 5.

**Resultado esperado:** Un libro con las hojas de datos, `KPIs` y `Analisis_IA`.

**Verificación:** El libro tiene las tres hojas.

## Validación y Pruebas

| Caso | Acción o prompt | Resultado esperado |
| :--- | :--- | :--- |
| Cobertura | Contar las filas de `Tabla_Metadatos` | 30 filas |
| Fidelidad | Revisar la fecha del documento 026 | `2024-04-31`, sin "corregir" |
| Prueba adversarial | Preguntar: *"¿Cuántos documentos envió la Dirección de Comunicación Social?"* | La IA indica que el lote no contiene documentos de esa área |

## Solución de Problemas

### Problema 1: La tabla se pega en una sola columna

- **Síntomas:** Todo el contenido queda en la columna A.
- **Causa:** La IA entregó texto con barras o tabulaciones en lugar de una tabla.
- **Solución:** Pedir: *"Entrega el resultado como tabla"*, o usar **Datos > Texto en columnas** con el delimitador correspondiente (barra vertical o tabulación).

### Problema 2: La IA omite documentos o se interrumpe

- **Síntomas:** La tabla tiene menos de 30 filas o la respuesta se corta.
- **Causa:** Límites de longitud de la versión gratuita.
- **Solución:** Pedir *"Continúa desde el documento N"* o usar el lote reducido de 15 documentos.

## Limpieza

1. Conservar `Consolidado_Metadatos_KPIs_[INICIALES].xlsx`.
2. Eliminar la conversación si la política institucional lo indica.

## Resumen

- Se definió un esquema de metadatos y se clasificó un lote completo de documentos con un prompt de control.
- Se calcularon KPIs de volumen, urgencia y tiempo de atención con tablas dinámicas.
- La IA ayudó a detectar anomalías e inconsistencias, y cada hallazgo se respaldó con el ID del documento.

---

[⬅ Anterior: Práctica 4](../Practica04/README.md) | [Inicio](../../README.md) | [Siguiente: Práctica 6 ➡](../../Capitulo03/Practica06/README.md)
