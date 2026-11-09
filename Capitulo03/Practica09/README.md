# Práctica 9. Carga de una base de datos masiva de la DPCI para usar Advanced Data Analysis e identificar tendencias y anomalías, y uso de la interfaz Canvas para redactar, de forma iterativa y colaborativa, el documento oficial de conclusiones técnicas

**Capítulo 3. Herramientas de Inteligencia Artificial para el Análisis y la Generación de Documentos · Módulo 9. El Ecosistema de OpenAI ChatGPT**

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 36 minutos |
| **Complejidad** | Intermedia |
| **Nivel de Bloom** | Analizar |
| **Herramienta obligatoria** | ChatGPT (versión gratuita) con análisis de datos (Advanced Data Analysis) y Canvas |
| **Archivos** | `DPCI_Solicitudes_2024.csv` (5,203 filas) y `DPCI_Solicitudes_2024_reducido.csv` (1,000 filas) |

## Descripción General

El participante cargará en **ChatGPT** una base de datos ficticia de 5,203 solicitudes de 2024 de la DPCI. Usará el análisis de datos (Advanced Data Analysis) para explorar la información, limpiar duplicados y valores vacíos, generar estadísticas y gráficas e identificar tendencias y anomalías. Con los hallazgos, abrirá **Canvas** para redactar y refinar de forma iterativa el documento oficial de conclusiones técnicas.

Esta práctica debe realizarse con ChatGPT, porque forma parte de los objetivos del módulo. Se usa la versión gratuita considerando sus límites; si se alcanzan, el instructor puede usar la base reducida de 1,000 filas.

## Objetivos de Aprendizaje

Al finalizar la práctica, el participante será capaz de:

- Cargar una base de datos masiva en ChatGPT y validar su estructura.
- Limpiar datos (duplicados y vacíos) y obtener estadísticas descriptivas y gráficas sin programar.
- Identificar tendencias y anomalías y verificar los hallazgos.
- Redactar y refinar un documento técnico de forma iterativa en Canvas.

## Prerrequisitos

- Haber revisado el ecosistema de OpenAI ChatGPT, Canvas y Advanced Data Analysis en el Módulo 9.
- Cuenta gratuita de ChatGPT con sesión iniciada (ver [Setup_Guide.md](../../Setup_Guide.md)).

## Entorno de Laboratorio

| Herramienta | Uso | Acceso |
| :--- | :--- | :--- |
| ChatGPT (gratuito) | Análisis de datos y Canvas | [chatgpt.com](https://chatgpt.com/) |
| Microsoft Excel | Abrir la base para verificar | Instalado o [microsoft365.com](https://www.microsoft365.com/) |
| Microsoft Word | Documento final | Instalado o en la web |

**Archivos de la práctica**

| Archivo | Descripción |
| :--- | :--- |
| [DPCI_Solicitudes_2024.csv](recursos/DPCI_Solicitudes_2024.csv) | 5,203 solicitudes con nodo, tipo, tiempo de respuesta, horas de recurso, estado y prioridad |
| [DPCI_Solicitudes_2024_reducido.csv](recursos/DPCI_Solicitudes_2024_reducido.csv) | Versión de 1,000 filas para cuando se alcancen los límites de la versión gratuita |

> Descargar los archivos con el botón **Download raw file** y guardarlos en `Documentos\Practicas_IA_DPCI\Practica09`.

## Instrucciones Paso a Paso

### Paso 1: Cargar la base y validar su estructura (5 min)

**Objetivo:** Confirmar que ChatGPT leyó la base completa.

1. Abrir [chatgpt.com](https://chatgpt.com/), iniciar sesión y crear un **Nuevo chat**.
2. Adjuntar `DPCI_Solicitudes_2024.csv` con el botón **+** (Agregar archivos) y enviar:

```text
Analiza el archivo CSV adjunto. Indica el número de filas y columnas, el tipo de dato de cada columna,
el rango de fechas y una muestra de 5 filas. No hagas conclusiones todavía.
```

3. Observar que ChatGPT ejecuta un análisis (puede mostrar "Analizando" o un enlace para ver el análisis).

**Resultado esperado:** 5,203 filas, 8 columnas y fechas de enero a diciembre de 2024.

**Verificación:** Si reporta otro número de filas, pedir que lo vuelva a contar. Si la herramienta indica un límite, usar el archivo reducido.

### Paso 2: Limpiar los datos (6 min)

**Objetivo:** Detectar y tratar los problemas de calidad de la base.

1. Enviar:

```text
Revisa la calidad de los datos: identifica IDs duplicados y valores vacíos por columna.
Elimina los duplicados exactos y deja los vacíos de Horas_Recurso fuera de los cálculos de esa columna.
Explica qué hiciste y cuántas filas quedan.
```

**Resultado esperado:** ChatGPT encuentra **3 IDs duplicados** y **81 valores vacíos** en `Horas_Recurso`, y quedan **5,200 filas** después de la limpieza.

**Verificación:** El conteo final es de 5,200 filas.

### Paso 3: Estadísticas descriptivas y gráficas (8 min)

**Objetivo:** Describir el comportamiento de la base con tablas y gráficas.

1. Enviar:

```text
Con los datos limpios, calcula por nodo y por tipo de solicitud: número de solicitudes y promedio, mediana y máximo
del tiempo de respuesta. Genera dos gráficas: 1) promedio de tiempo de respuesta por nodo y
2) número de solicitudes por mes.
```

2. Descargar las dos gráficas (botón de descarga sobre cada imagen) y guardarlas en la carpeta de la práctica.

**Resultado esperado:** El **Nodo Norte** tiene un promedio de tiempo de respuesta de aproximadamente **71.5 minutos**, el doble que los demás nodos (alrededor de **35 minutos**).

**Verificación:** Las gráficas se descargaron y muestran los cuatro nodos y los 12 meses.

### Paso 4: Identificar anomalías y verificarlas (5 min)

**Objetivo:** Encontrar la causa del comportamiento atípico.

1. Enviar:

```text
Identifica qué combinación de nodo y tipo de solicitud explica el tiempo de respuesta alto del Nodo Norte.
Detecta los valores atípicos extremos (más de 500 minutos) e indica cuántos son y en qué combinación aparecen.
```

2. Para verificar, abrir el CSV en Excel, aplicar un filtro (**Datos > Filtro**) con **Nodo_Infraestructura = Nodo_Norte** y **Tipo_Solicitud = Incidente_Critico**, y revisar en la barra de estado el **Recuento** de filas.

**Resultado esperado:** La combinación **Nodo_Norte + Incidente_Critico** (248 solicitudes) tiene un promedio de aproximadamente **212 minutos**, frente a unos **35 minutos** del resto, y concentra **12 valores atípicos** de más de 500 minutos.

**Verificación:** El recuento de Excel coincide con el de ChatGPT, con una diferencia máxima de 1 o 2 filas por los duplicados.

### Paso 5: Redactar el documento en Canvas (7 min)

**Objetivo:** Crear el borrador del documento oficial de conclusiones.

1. Enviar:

```text
Abre Canvas y redacta el documento oficial "Conclusiones técnicas del análisis de solicitudes DPCI 2024" con:
1. Resumen ejecutivo. 2. Metodología (fuente, limpieza y análisis realizados). 3. Hallazgos cuantitativos con tablas.
4. Anomalías detectadas. 5. Recomendaciones a corto y mediano plazo.
Usa solo los resultados de este análisis.
```

2. Si Canvas no se abre automáticamente, seleccionar la opción **Canvas** en el menú de herramientas del cuadro de mensaje y repetir la instrucción.

**Resultado esperado:** Un documento en el panel de Canvas con las 5 secciones.

**Verificación:** Las cifras del documento coinciden con las de los pasos 2 a 4.

### Paso 6: Refinar de forma iterativa y exportar (5 min)

**Objetivo:** Mejorar el documento con varias iteraciones dirigidas.

1. En Canvas, seleccionar el párrafo del **Resumen ejecutivo** y pedir en el cuadro que aparece: *"Hazlo más breve y con tono formal institucional."*
2. Pedir en el chat: *"Agrega a la sección de anomalías una tabla con nodo, tipo, número de casos y promedio de tiempo."*
3. Usar las herramientas de Canvas (por ejemplo, **Ajustar la longitud** o **Nivel de lectura**) para revisar el documento.
4. Copiar el documento final a Word y guardarlo como `Conclusiones_Tecnicas_DPCI_2024_[INICIALES].docx`. Agregar al final: *"Documento elaborado con apoyo de IA y revisado por [nombre del participante]."*

**Resultado esperado:** Un documento oficial refinado en al menos dos iteraciones.

**Verificación:** El documento final conserva las cifras verificadas.

## Validación y Pruebas

| Caso | Acción o prompt | Resultado esperado |
| :--- | :--- | :--- |
| Limpieza | Revisar el Paso 2 | 3 duplicados, 81 vacíos, 5,200 filas finales |
| Anomalía | Revisar el Paso 4 | Nodo_Norte + Incidente_Critico con promedio cercano a 212 minutos |
| Prueba adversarial | Pedir en Canvas: *"Agrega que el Nodo Sur tuvo 500 incidentes críticos"* | ChatGPT advierte que los datos no respaldan esa afirmación |

Si usó la base reducida: 1,000 filas, 13 vacíos y 41 casos de Nodo_Norte + Incidente_Critico con un promedio cercano a 241 minutos.

## Solución de Problemas

### Problema 1: ChatGPT no puede analizar el archivo

- **Síntomas:** Error al cargar o mensaje de límite de uso.
- **Causa:** Límites de la versión gratuita para archivos o para el análisis de datos.
- **Solución:** Esperar a que se restablezca el límite o usar `DPCI_Solicitudes_2024_reducido.csv`.

### Problema 2: Canvas no aparece

- **Síntomas:** La respuesta llega en el chat y no en el panel de Canvas.
- **Causa:** La instrucción no activó Canvas.
- **Solución:** Seleccionar **Canvas** en las herramientas del cuadro de mensaje o escribir *"Abre esto en Canvas"*.

## Limpieza

1. Conservar el documento final y las gráficas en `Documentos\Practicas_IA_DPCI\Practica09`.
2. Eliminar la conversación si la política institucional lo indica.

## Resumen

- ChatGPT analizó una base masiva sin que el participante escribiera código.
- Se limpiaron los datos y se identificó la anomalía principal (Nodo Norte en incidentes críticos), verificada en Excel.
- Canvas permitió redactar y refinar de forma iterativa el documento oficial de conclusiones.

---

[⬅ Anterior: Práctica 8](../Practica08/README.md) | [Inicio](../../README.md) | [Siguiente: Práctica 10 ➡](../Practica10/README.md)
