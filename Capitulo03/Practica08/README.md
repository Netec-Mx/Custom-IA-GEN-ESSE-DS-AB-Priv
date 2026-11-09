# Práctica 8. Uso avanzado de NotebookLM alimentado con el histórico de normativas, manuales y documentos generados por la DPCI para crear un repositorio inteligente de consulta rápida, síntesis profunda y redacción de materiales de capacitación

**Capítulo 3. Herramientas de Inteligencia Artificial para el Análisis y la Generación de Documentos · Módulo 8. El Ecosistema de Google Gemini para el análisis de conocimiento**

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 36 minutos |
| **Complejidad** | Intermedia |
| **Nivel de Bloom** | Crear |
| **Herramienta obligatoria** | Google NotebookLM (versión gratuita) |
| **Archivos** | 6 documentos normativos ficticios en PDF |

## Descripción General

El participante creará un cuaderno en **NotebookLM** con el acervo normativo ficticio de la DPCI: una norma vigente y su versión histórica, un manual, una política, una guía y una circular. Lo usará como repositorio inteligente: hará **consultas rápidas** verificando las citas a las fuentes, pedirá **síntesis comparativas** entre documentos (incluida la evolución de la norma y una excepción temporal) y usará las herramientas del cuaderno para producir **materiales de capacitación**.

Esta práctica debe realizarse con NotebookLM, porque forma parte de los objetivos del módulo. Se usa su versión gratuita; el instructor puede reducir el número de fuentes si es necesario.

## Objetivos de Aprendizaje

Al finalizar la práctica, el participante será capaz de:

- Crear un cuaderno de NotebookLM alimentado con un acervo documental.
- Hacer consultas respondidas solo con las fuentes y verificar sus citas.
- Generar síntesis comparativas entre documentos, versiones y excepciones.
- Producir materiales de capacitación a partir de las fuentes.

## Prerrequisitos

- Haber revisado el ecosistema de Google Gemini y NotebookLM en el Módulo 8.
- Cuenta de Google con acceso a NotebookLM (ver [Setup_Guide.md](../../Setup_Guide.md)).

## Entorno de Laboratorio

| Herramienta | Uso | Acceso |
| :--- | :--- | :--- |
| Google NotebookLM | Repositorio inteligente | [notebooklm.google.com](https://notebooklm.google.com/) |
| Microsoft Word o Google Docs | Material de capacitación final | Instalado o en la web |

**Archivos de la práctica**

| Archivo | Descripción |
| :--- | :--- |
| [NOR_001_Seguridad_2024.pdf](recursos/NOR_001_Seguridad_2024.pdf) | Norma vigente de seguridad de la información |
| [NOR_001_Seguridad_2021_HISTORICA.pdf](recursos/NOR_001_Seguridad_2021_HISTORICA.pdf) | Versión histórica abrogada de la misma norma |
| [MAN_002_Incidentes.pdf](recursos/MAN_002_Incidentes.pdf) | Manual de respuesta a incidentes |
| [POL_003_Uso_IA.pdf](recursos/POL_003_Uso_IA.pdf) | Política de uso responsable de IA |
| [GUI_004_Bitacoras.pdf](recursos/GUI_004_Bitacoras.pdf) | Guía de auditoría de bitácoras |
| [CIR_005_Contrasenas.pdf](recursos/CIR_005_Contrasenas.pdf) | Circular con una excepción temporal a la política de contraseñas |

> Descargar los 6 archivos con el botón **Download raw file** y guardarlos en `Documentos\Practicas_IA_DPCI\Practica08`.

## Instrucciones Paso a Paso

### Paso 1: Crear el cuaderno (3 min)

**Objetivo:** Tener un cuaderno vacío para el acervo de la DPCI.

1. Abrir [notebooklm.google.com](https://notebooklm.google.com/) e iniciar sesión con la cuenta de Google indicada por el instructor.
2. Seleccionar **Crear cuaderno** (o **Nuevo cuaderno**).
3. Cambiar el nombre del cuaderno (clic en el título) a `Acervo normativo DPCI - [INICIALES]`.

**Resultado esperado:** Un cuaderno nuevo con el panel de fuentes abierto.

**Verificación:** El título del cuaderno muestra el nombre asignado.

### Paso 2: Cargar las fuentes (4 min)

**Objetivo:** Alimentar el cuaderno con el acervo completo.

1. En el panel **Fuentes**, seleccionar **Agregar** > **Subir archivos** y elegir los 6 PDF de la práctica.
2. Esperar a que las 6 fuentes aparezcan con su nombre en el panel.
3. Leer el resumen automático que NotebookLM genera del cuaderno.

**Resultado esperado:** 6 fuentes cargadas y un resumen general del acervo.

**Verificación:** El panel de fuentes muestra los 6 documentos, todos con la casilla marcada.

### Paso 3: Consultas rápidas con verificación de citas (7 min)

**Objetivo:** Usar el cuaderno como repositorio de consulta y comprobar sus fuentes.

1. En el chat del cuaderno, hacer estas tres consultas, una por una:

```text
¿Cuál es el tiempo máximo de primera respuesta para un incidente crítico y qué lo define como crítico?
```

```text
¿Qué está prohibido introducir en herramientas de IA generativa comerciales?
```

```text
¿Cada cuánto deben rotarse las contraseñas en la DPCI? Considera todas las fuentes vigentes.
```

2. En cada respuesta, hacer clic en los números de cita para abrir el fragmento de la fuente y comprobar que respalda la afirmación.
3. En la tercera consulta, verificar que la respuesta combine dos fuentes: la norma vigente (**90 días**) y la circular (**120 días** para sistemas heredados, hasta el 31 de diciembre de 2024).

**Resultado esperado:** Respuestas citadas: 15 minutos para incidentes críticos (manual), la prohibición de introducir datos personales y credenciales (política) y la regla de 90 días con su excepción temporal.

**Verificación:** Cada respuesta tiene al menos una cita y la cita abre el fragmento correcto.

### Paso 4: Síntesis comparativa y detección de vacíos (7 min)

**Objetivo:** Obtener análisis que combinen varios documentos.

1. Enviar:

```text
Compara la versión histórica 2021 y la versión vigente 2024 de la norma DPCI-NOR-001 en una tabla:
tema, versión 2021, versión 2024 y cambio. Incluye MFA, longitud de contraseña, rotación y aviso previo de cambios.
```

2. Verificar los cambios: MFA de **recomendable** a **obligatorio**, contraseña de **8 a 16 caracteres**, rotación de **180 a 90 días** y aviso de cambios de **24 a 48 horas**.
3. Enviar:

```text
Identifica temas relacionados con seguridad y uso de IA que no estén regulados en ninguna de las fuentes,
o que estén regulados de forma contradictoria. Cita las fuentes en las que te basas.
```

4. Anotar dos vacíos o contradicciones que considere relevantes.

**Resultado esperado:** Una tabla comparativa correcta y una lista de vacíos con citas.

**Verificación:** La tabla no presenta como vigente ninguna regla de la versión 2021.

### Paso 5: Generar materiales de estudio (7 min)

**Objetivo:** Usar las herramientas del cuaderno para crear apoyos de capacitación.

1. En el panel **Studio** (o en las opciones de generación del cuaderno), crear una **Guía de estudio** y unas **Preguntas frecuentes**. Si está disponible, generar también un **Mapa mental** o un **Resumen en audio**.
2. Revisar la guía de estudio: comprobar que no incluya reglas de la versión histórica como si estuvieran vigentes.
3. Guardar en el cuaderno el material útil como nota (opción **Guardar en nota**, si aparece).

**Resultado esperado:** Al menos dos materiales generados a partir de las fuentes.

**Verificación:** Las preguntas frecuentes responden con las reglas vigentes.

### Paso 6: Redactar el material de capacitación (8 min)

**Objetivo:** Producir un material de capacitación listo para revisión.

1. Enviar:

```text
Redacta un material de capacitación de una página para personal de nuevo ingreso sobre seguridad de la información
y uso responsable de IA en la DPCI. Incluye: objetivo, 5 reglas clave con su fuente, un caso práctico breve
y 3 preguntas de evaluación de opción múltiple con su respuesta correcta. Usa solo las fuentes vigentes.
```

2. Copiar la respuesta, pegarla en un documento de Word o de Google Docs y revisar que cada regla tenga su fuente.
3. Guardar como `Material_Capacitacion_DPCI_[INICIALES].docx`.

**Resultado esperado:** Un material de capacitación con reglas citadas, un caso práctico y una evaluación.

**Verificación:** Ninguna regla proviene solo de la versión histórica de 2021.

## Validación y Pruebas

| Caso | Acción o prompt | Resultado esperado |
| :--- | :--- | :--- |
| Citas | Abrir dos citas del Paso 3 | El fragmento citado respalda la respuesta |
| Versiones | Revisar la tabla del Paso 4 | Los cuatro cambios entre 2021 y 2024 son correctos |
| Prueba adversarial | Preguntar: *"¿Qué dice la ley federal de protección de datos sobre las contraseñas?"* | NotebookLM indica que las fuentes no contienen esa información |

## Solución de Problemas

### Problema 1: Un archivo no se carga

- **Síntomas:** La fuente aparece con error o no aparece.
- **Causa:** Formato no admitido o límite de fuentes.
- **Solución:** Volver a subir el PDF. Si persiste, abrir el PDF, copiar su texto y agregarlo como fuente de **Texto copiado**.

### Problema 2: Las respuestas mezclan la versión histórica con la vigente

- **Síntomas:** La respuesta indica 8 caracteres o 180 días como regla actual.
- **Causa:** La consulta no especificó la vigencia.
- **Solución:** Agregar a la consulta *"Usa solo las fuentes vigentes"*, o desmarcar temporalmente la fuente histórica en el panel de fuentes.

## Limpieza

1. Conservar el cuaderno y `Material_Capacitacion_DPCI_[INICIALES].docx`.
2. Si la política institucional lo indica, eliminar el cuaderno al finalizar el curso (menú **⋮** del cuaderno > **Eliminar**).

## Resumen

- Se creó un repositorio inteligente en NotebookLM con un acervo normativo y su histórico.
- Las consultas se respondieron con citas verificables a las fuentes.
- Se compararon versiones, se conciliaron excepciones y se detectaron vacíos.
- Se generaron materiales de capacitación basados solo en las fuentes vigentes.

---

[⬅ Anterior: Práctica 7](../Practica07/README.md) | [Inicio](../../README.md) | [Siguiente: Práctica 9 ➡](../Practica09/README.md)
