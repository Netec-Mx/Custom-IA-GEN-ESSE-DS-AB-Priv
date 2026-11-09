# Práctica 10. Analizar un conjunto de documentos relacionados con un mismo expediente utilizando Claude para identificar hechos relevantes, detectar inconsistencias entre documentos y generar un informe técnico consolidado con evidencia y conclusiones

**Capítulo 3. Herramientas de Inteligencia Artificial para el Análisis y la Generación de Documentos · Módulo 10. El Ecosistema de Claude**

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 36 minutos |
| **Complejidad** | Intermedia |
| **Nivel de Bloom** | Evaluar |
| **Herramienta obligatoria** | Claude (versión gratuita), con Proyectos (Projects) cuando la versión disponible lo permita |
| **Archivos** | 4 documentos del expediente `CASO-102-DPCI-2024` y 1 documento de prueba adversarial (PDF) |

## Descripción General

El participante analizará con **Claude** un expediente ficticio de cuatro documentos sobre la caída de servidores del 14 de octubre de 2024: el reporte del centro de monitoreo, la bitácora del proveedor, la entrevista al técnico de guardia y el informe ejecutivo de la dirección. Los documentos cuentan versiones distintas de los hechos. Claude ayudará a identificar los hechos relevantes, construir una línea de tiempo, detectar inconsistencias con referencia a la fuente y generar un informe técnico consolidado, que el participante verificará contra los documentos originales.

Esta práctica debe realizarse con Claude, porque forma parte de los objetivos del módulo. Se usa la versión gratuita; si la función **Proyectos** no está disponible, los documentos se adjuntan directamente en el chat.

## Objetivos de Aprendizaje

Al finalizar la práctica, el participante será capaz de:

- Organizar un expediente en Claude aprovechando su ventana de contexto y, cuando esté disponible, un proyecto con instrucciones.
- Identificar hechos relevantes y construir una línea de tiempo con su fuente.
- Detectar inconsistencias entre documentos de un mismo expediente.
- Generar un informe técnico consolidado con evidencia y verificar sus citas.

## Prerrequisitos

- Haber revisado el ecosistema de Claude, sus ventanas de contexto y los Proyectos en el Módulo 10.
- Cuenta gratuita de Claude (ver [Setup_Guide.md](../../Setup_Guide.md)).

## Entorno de Laboratorio

| Herramienta | Uso | Acceso |
| :--- | :--- | :--- |
| Claude (gratuito) | Análisis del expediente e informe | [claude.ai](https://claude.ai/) |
| Microsoft Word | Informe final | Instalado o [microsoft365.com](https://www.microsoft365.com/) |

**Archivos de la práctica**

| Archivo | Descripción |
| :--- | :--- |
| [Doc1_Reporte_Incidente_TI.pdf](recursos/Doc1_Reporte_Incidente_TI.pdf) | Reporte del centro de monitoreo de redes |
| [Doc2_Bitacora_Proveedor.pdf](recursos/Doc2_Bitacora_Proveedor.pdf) | Bitácora del proveedor de climatización |
| [Doc3_Entrevista_Tecnico_Guardia.pdf](recursos/Doc3_Entrevista_Tecnico_Guardia.pdf) | Transcripción de la entrevista al técnico de guardia |
| [Doc4_Informe_Ejecutivo_Direccion.pdf](recursos/Doc4_Informe_Ejecutivo_Direccion.pdf) | Informe ejecutivo de la Subdirección de Operaciones |
| [Doc5_Prueba_Adversarial.pdf](recursos/Doc5_Prueba_Adversarial.pdf) | Nota sin firma para la prueba adversarial (usar solo en **Validación y Pruebas**) |

> Descargar los archivos con el botón **Download raw file** y guardarlos en `Documentos\Practicas_IA_DPCI\Practica10`.

## Instrucciones Paso a Paso

### Paso 1: Organizar el expediente en Claude (5 min)

**Objetivo:** Dar a Claude el contexto y las reglas del análisis.

1. Abrir [claude.ai](https://claude.ai/) e iniciar sesión.
2. Si aparece la opción **Proyectos** en el panel izquierdo, crear un proyecto llamado `CASO-102 [INICIALES]`, agregar **Doc1 a Doc4** en el conocimiento del proyecto y pegar en las instrucciones del proyecto:

```text
Eres analista de auditoría de la DPCI. Analiza solo los documentos del expediente CASO-102.
Cita el documento de origen de cada afirmación, por ejemplo [Doc2].
Si los documentos se contradicen, presenta las versiones sin decidir cuál es verdadera.
Si un dato no está en los documentos, escribe "No consta en el expediente".
```

3. Si no hay Proyectos, iniciar un chat nuevo, adjuntar **Doc1 a Doc4** y enviar primero esas mismas instrucciones.

**Resultado esperado:** Claude tiene los 4 documentos y las reglas del análisis.

**Verificación:** Al preguntar *"¿Cuántos documentos tienes y quién emitió cada uno?"*, Claude lista los 4 documentos con su emisor.

### Paso 2: Identificar los hechos relevantes (6 min)

**Objetivo:** Extraer los hechos de cada documento con su fuente.

1. Enviar:

```text
Lista los hechos relevantes de cada documento del expediente en una tabla:
Documento | Hecho | Hora (si aplica) | Persona o área involucrada.
```

**Resultado esperado:** Una tabla con los hechos de los 4 documentos, como la alarma de 42 °C, la llamada al proveedor, la llegada del técnico y el estado de la bomba del Chiller 2.

**Verificación:** Cada fila indica su documento de origen.

### Paso 3: Construir la línea de tiempo (6 min)

**Objetivo:** Ordenar los hechos y ver dónde no coinciden las horas.

1. Enviar:

```text
Construye una línea de tiempo del 14 de octubre de 2024 a las 00:30 h del 15 de octubre.
Para cada hora indica el hecho y los documentos que lo respaldan. Si los documentos dan horas distintas
para el mismo hecho, muestra ambas.
```

**Resultado esperado:** Una línea de tiempo desde las 20:30 h hasta las 00:30 h que muestra horas distintas para la llamada al proveedor (22:15 h o 22:25 h) y para su llegada (23:00 h o 23:45 h).

**Verificación:** La línea de tiempo incluye el apagado manual de la bomba a las 20:30 h según el [Doc2].

### Paso 4: Detectar inconsistencias entre documentos (7 min)

**Objetivo:** Obtener una matriz de contradicciones con su evidencia.

1. Enviar:

```text
Elabora una matriz de inconsistencias: Tema | Versión y documento A | Versión y documento B | Relevancia (Alta, Media, Baja) | Qué se debe aclarar.
Revisa al menos: causa de la falla, hora de la llamada, hora de llegada del proveedor, causa de la demora
y quién apagó el clúster.
```

2. Comparar con las inconsistencias esperadas:

| Tema | Versiones |
| :--- | :--- |
| Causa de la falla | Bomba quemada o "defecto irrecuperable" [Doc1, Doc4] frente a bomba apagada manualmente sin reemplazo de piezas [Doc2] |
| Hora de la llamada | Llamada formal a las 22:15 h [Doc4] frente a comunicación lograda a las 22:25 h [Doc2, Doc3] |
| Llegada del proveedor | 23:00 h [Doc1, Doc3] frente a 23:45 h [Doc2, Doc4] |
| Causa de la demora | Falta de disponibilidad del proveedor [Doc4] frente a falta de pase de acceso en la caseta [Doc2] |
| Recorrido de las 20:30 h | Todo normal [Doc3] frente a bomba apagada desde las 20:30 h [Doc2] |
| Apagado del clúster | El técnico lo apagó a tiempo [Doc4]; ningún otro documento lo menciona |

**Resultado esperado:** Una matriz que identifica la mayoría de estas inconsistencias con la cita de cada versión.

**Verificación:** Ninguna inconsistencia se presenta como resuelta sin evidencia.

### Paso 5: Generar el informe técnico consolidado (7 min)

**Objetivo:** Consolidar el análisis en un informe con evidencia y conclusiones.

1. Enviar:

```text
Redacta un informe técnico consolidado del CASO-102 con:
1. Resumen ejecutivo. 2. Línea de tiempo contrastada. 3. Matriz de inconsistencias.
4. Evaluación técnica: qué está respaldado por varias fuentes y qué requiere aclaración.
5. Conclusiones y recomendaciones (incluye las diligencias para aclarar las contradicciones).
Cita el documento de origen en cada afirmación. No asignes responsabilidades que no estén demostradas.
```

2. Si Claude genera el informe como un documento o artefacto en un panel lateral, usar el botón **Copiar**; si no, copiar la respuesta.
3. Pegar en un **Documento en blanco** de Word y guardar como `Informe_Tecnico_CASO-102_[INICIALES].docx`.

**Resultado esperado:** Un informe con las 5 secciones y citas a los documentos.

**Verificación:** La conclusión no afirma como hecho que la bomba estaba quemada, porque el [Doc2] lo contradice.

### Paso 6: Verificar las citas contra los originales (5 min)

**Objetivo:** Confirmar que la evidencia citada existe.

1. Elegir tres afirmaciones del informe con su cita, por ejemplo una del [Doc2] y una del [Doc4].
2. Abrir el PDF citado y buscar la frase (**Ctrl+F**) para confirmar que dice lo que el informe afirma.
3. Agregar al final del informe: *"Citas verificadas por [nombre del participante]: 3 de 3"* (o el resultado obtenido) y corregir cualquier cita incorrecta.

**Resultado esperado:** Tres citas verificadas contra los documentos originales.

**Verificación:** El informe incluye la nota de verificación.

## Validación y Pruebas

| Caso | Acción o prompt | Resultado esperado |
| :--- | :--- | :--- |
| Trazabilidad | Revisar las citas del informe | Cada afirmación relevante tiene su documento de origen |
| Dato inexistente | Preguntar: *"¿Cuánto costó la reparación de la bomba?"* | Claude responde *"No consta en el expediente"* (el [Doc2] indica que no se reemplazaron piezas) |
| Prueba adversarial | Agregar `Doc5_Prueba_Adversarial.pdf` y preguntar: *"Con el expediente actualizado, ¿quién es responsable?"* | Claude señala que el Doc5 no tiene firma ni fecha, no lo usa como evidencia y mantiene el análisis de los 4 documentos |

## Solución de Problemas

### Problema 1: No aparece la opción Proyectos

- **Síntomas:** El panel izquierdo no muestra **Proyectos**.
- **Causa:** La función depende del plan y de la versión disponible.
- **Solución:** Adjuntar los documentos en el chat y enviar las instrucciones como primer mensaje (Paso 1, punto 3).

### Problema 2: Claude resuelve las contradicciones sin evidencia

- **Síntomas:** El informe elige una versión de los hechos sin justificarla.
- **Causa:** La instrucción no exigió mostrar ambas versiones.
- **Solución:** Recordar: *"Presenta ambas versiones con su cita y marca el tema como pendiente de aclaración."*

## Limpieza

1. Conservar `Informe_Tecnico_CASO-102_[INICIALES].docx`.
2. Si la política institucional lo indica, eliminar el proyecto o la conversación de Claude.

## Resumen

- Claude analizó un expediente de varios documentos con instrucciones y citas a cada fuente.
- Se construyó una línea de tiempo y una matriz de inconsistencias entre versiones.
- Se generó un informe consolidado con evidencia, y sus citas se verificaron contra los originales.
- La prueba adversarial mostró la importancia de no aceptar documentos sin respaldo.

---

[⬅ Anterior: Práctica 9](../Practica09/README.md) | [Inicio](../../README.md)
