# Práctica 7. Análisis automático de un archivo de Excel institucional con Copilot; generación de un informe ejecutivo estructurado en Word (objetivos, alcances, políticas, métricas y glosario) y creación automatizada de su presentación en PowerPoint

**Capítulo 3. Herramientas de Inteligencia Artificial para el Análisis y la Generación de Documentos · Módulo 7. El Ecosistema de Microsoft Copilot para el análisis documental**

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 36 minutos |
| **Complejidad** | Intermedia |
| **Nivel de Bloom** | Aplicar |
| **Herramienta obligatoria** | Microsoft Copilot Chat (versión gratuita), con Word y PowerPoint para revisar los entregables |
| **Archivos** | `DPCI_Metricas_Operativas_2024.xlsx` |

## Descripción General

El participante cargará en **Microsoft Copilot Chat** un archivo de Excel ficticio con las métricas operativas mensuales de 2024 de cuatro nodos de la DPCI. Pedirá a Copilot analizar la información para identificar métricas, tendencias y hallazgos; a partir de ese análisis, generará el contenido de un **informe ejecutivo para Word** (objetivos, alcances, políticas, métricas y glosario) y la estructura de una **presentación de PowerPoint**, que descargará o copiará desde Copilot.

Esta práctica debe realizarse con Microsoft Copilot, porque forma parte de los objetivos del módulo. Se usa la versión gratuita de Copilot Chat mediante la carga de archivos, **sin requerir licencia Premium ni Copilot integrado en las aplicaciones de Office**. El instructor puede simplificar el escenario o reducir el archivo si se alcanzan los límites de la versión gratuita.

## Objetivos de Aprendizaje

Al finalizar la práctica, el participante será capaz de:

- Analizar un archivo de Excel con Copilot Chat para identificar métricas, tendencias y anomalías.
- Verificar las cifras de Copilot contra los datos originales.
- Generar con Copilot el contenido estructurado de un informe ejecutivo y de una presentación.
- Reconocer las consideraciones de privacidad al usar Copilot con información institucional.

## Prerrequisitos

- Haber revisado el ecosistema de Microsoft Copilot y su privacidad y gobernanza en el Módulo 7.
- Cuenta Microsoft para iniciar sesión en Copilot (ver [Setup_Guide.md](../../Setup_Guide.md)).
- Manejo básico de Excel, Word y PowerPoint.

## Entorno de Laboratorio

| Herramienta | Uso | Acceso |
| :--- | :--- | :--- |
| Microsoft Copilot Chat (gratuito) | Análisis del Excel y generación de contenidos | [copilot.microsoft.com](https://copilot.microsoft.com/) |
| Microsoft Excel | Verificar las cifras | Instalado o [microsoft365.com](https://www.microsoft365.com/) |
| Microsoft Word y PowerPoint | Armar y revisar los entregables | Instalados o [microsoft365.com](https://www.microsoft365.com/) |

**Archivos de la práctica**

| Archivo | Descripción |
| :--- | :--- |
| [DPCI_Metricas_Operativas_2024.xlsx](recursos/DPCI_Metricas_Operativas_2024.xlsx) | 48 registros (12 meses × 4 nodos) con peticiones, tiempo de respuesta, incidentes, SLA y presupuesto, más la hoja `Diccionario` |

> Descargar el archivo con el botón **Download raw file** y guardarlo en `Documentos\Practicas_IA_DPCI\Practica07`.

## Instrucciones Paso a Paso

### Paso 1: Iniciar sesión y revisar la privacidad (3 min)

**Objetivo:** Trabajar en Copilot con la cuenta adecuada y conocer cómo se protegen los datos.

1. Abrir [copilot.microsoft.com](https://copilot.microsoft.com/) e iniciar sesión con la cuenta indicada por el instructor.
2. Si inicia sesión con una cuenta de trabajo o escuela, comprobar si aparece un indicador de protección de datos empresariales (por ejemplo, un escudo junto al cuadro de mensaje). Con una cuenta personal, ese indicador no aparece.
3. Recordar la regla del curso: solo se cargan datos ficticios o anonimizados (ver [Práctica 2](../../Capitulo01/Practica02/README.md)).

**Resultado esperado:** Sesión iniciada y tipo de protección de datos identificado.

**Verificación:** El participante puede explicar si su sesión tiene o no protección de datos empresariales.

### Paso 2: Cargar el Excel y pedir el análisis (8 min)

**Objetivo:** Obtener métricas, tendencias y anomalías del archivo.

1. Iniciar una conversación nueva y adjuntar `DPCI_Metricas_Operativas_2024.xlsx` con el botón de adjuntar (**+** o clip).
2. Enviar este prompt:

```text
Analiza el archivo adjunto de métricas operativas 2024 de la DPCI (usa la hoja Diccionario para interpretar los campos).
1) Calcula por nodo: total de peticiones, promedio de tiempo de respuesta, total de incidentes críticos,
   promedio de SLA y presupuesto ejercido.
2) Compara el primer y el segundo semestre de cada nodo.
3) Identifica tendencias y anomalías, indicando los meses en que el SLA estuvo por debajo de 99.5 %
   y el tiempo de respuesta por encima de 25 minutos.
Presenta los resultados en tablas y explica los hallazgos en 5 viñetas.
```

3. Abrir el Excel en otra ventana, aplicar un filtro (**Datos > Filtro**) a la columna **Nodo**, seleccionar **Nodo Norte** y comprobar dos cifras de Copilot.

**Resultado esperado:** Copilot identifica que el **Nodo Norte** se degrada desde julio: el SLA cae de 97.5 % a 94.0 %, el tiempo de respuesta supera 25 minutos de octubre a diciembre (27.6, 30.8 y 34.0 min) y los incidentes críticos suben de 3 a 8 por mes. Los otros tres nodos se mantienen estables.

**Verificación:** El total de incidentes críticos del Nodo Norte es **42**; el total general de peticiones es **67,244**. Si Copilot reporta otras cifras, pedirle que muestre el cálculo y corregirlo.

### Paso 3: Generar el informe ejecutivo para Word (9 min)

**Objetivo:** Obtener el contenido del informe con las cinco secciones requeridas.

1. Enviar este prompt en la misma conversación:

```text
Con base en el análisis anterior, redacta un informe ejecutivo para la dirección de la DPCI con estas secciones:
1. Objetivos del informe.
2. Alcance y limitaciones (periodo, nodos y fuentes).
3. Políticas institucionales aplicables: uso responsable de IA, verificación humana de los resultados
   y protección de datos.
4. Métricas clave: una tabla por nodo con las cifras verificadas y los hallazgos principales.
5. Glosario técnico (SLA, incidente crítico, tiempo de respuesta, nodo y otros términos usados).
Usa un tono formal y máximo dos páginas. Si puedes generar un documento de Word descargable, hazlo.
```

2. Si Copilot ofrece un archivo descargable, descargarlo. Si no, abrir Word, crear un **Documento en blanco**, copiar la respuesta con el botón **Copiar** y pegarla con **Ctrl+V**.
3. Revisar que la tabla de métricas del documento coincida con las cifras verificadas en el Paso 2 y corregir las que no coincidan.
4. Guardar como `Informe_Ejecutivo_DPCI_2024_[INICIALES].docx`.

**Resultado esperado:** Un informe con las 5 secciones y cifras verificadas.

**Verificación:** El documento contiene las secciones Objetivos, Alcance, Políticas, Métricas y Glosario.

### Paso 4: Generar la presentación de PowerPoint (8 min)

**Objetivo:** Obtener una presentación ejecutiva coherente con el informe.

1. Enviar este prompt:

```text
Con base en el informe, prepara una presentación ejecutiva de 6 diapositivas:
1) Portada y contexto, 2) Métricas generales 2024, 3) Comparación por nodo, 4) Diagnóstico del Nodo Norte,
5) Recomendaciones, 6) Decisiones solicitadas a la dirección.
Para cada diapositiva da: título, 3 a 4 viñetas breves y una sugerencia de gráfico o imagen.
Si puedes generar un archivo de PowerPoint descargable, hazlo.
```

2. Si Copilot entrega un archivo de PowerPoint, descargarlo y abrirlo. Si no:
   - Abrir PowerPoint y crear una **Presentación en blanco**.
   - Crear las 6 diapositivas copiando el título y las viñetas de cada una.
   - Usar **Diseño > Diseñador** (si está disponible) para aplicar un diseño.
3. Guardar como `Presentacion_Ejecutiva_DPCI_2024_[INICIALES].pptx`.

**Resultado esperado:** Una presentación de 6 diapositivas alineada con el informe.

**Verificación:** La diapositiva 4 menciona la caída del SLA del Nodo Norte en el segundo semestre.

### Paso 5: Crear una infografía de apoyo (5 min)

**Objetivo:** Explorar la generación de un entregable visual descargable.

1. Enviar: *"Crea una infografía con los 3 hallazgos principales del análisis y los datos del Nodo Norte."*
2. Si Copilot genera una imagen, descargarla y revisar que las cifras sean correctas; las imágenes generadas pueden tener errores en los números.
3. Registrar en una nota si la infografía es utilizable o qué cifras tiene mal.

**Resultado esperado:** Una infografía descargada o la limitación documentada.

**Verificación:** Las cifras de la infografía se compararon con las verificadas en el Paso 2.

### Paso 6: Revisión final (3 min)

1. Abrir el informe y la presentación y comprobar que las cifras coinciden entre sí y con el Excel.
2. Agregar al final del informe la leyenda: *"Documento elaborado con apoyo de IA y revisado por [nombre del participante]."*

**Resultado esperado:** Entregables coherentes y con la revisión humana documentada.

**Verificación:** El informe incluye la leyenda de revisión.

## Validación y Pruebas

| Caso | Acción o prompt | Resultado esperado |
| :--- | :--- | :--- |
| Exactitud | Comparar el total de incidentes del Nodo Norte | 42 en Copilot, en Excel y en el informe |
| Coherencia | Comparar el informe con la presentación | Las mismas cifras y conclusiones |
| Prueba adversarial | Preguntar: *"¿Cuál fue el SLA del Nodo Norte en enero de 2025?"* | Copilot indica que el archivo solo contiene datos de 2024 |

## Solución de Problemas

### Problema 1: Copilot no puede leer el archivo

- **Síntomas:** Mensaje de error al adjuntar o respuesta sin datos.
- **Causa:** Límite de tamaño o tipo de archivo de la versión gratuita, o sesión no iniciada.
- **Solución:** Iniciar sesión, volver a adjuntar el archivo o copiar el rango de datos desde Excel y pegarlo en el chat.

### Problema 2: Copilot no genera archivos descargables

- **Síntomas:** Solo entrega texto.
- **Causa:** La función de exportación depende de la versión y la región.
- **Solución:** Copiar el contenido a Word y PowerPoint como se indica en los pasos 3 y 4; el objetivo se cumple igual.

## Limpieza

1. Conservar el informe, la presentación y la infografía en `Documentos\Practicas_IA_DPCI\Practica07`.
2. Eliminar la conversación de Copilot si la política institucional lo indica.

## Resumen

- Copilot Chat analizó un Excel institucional e identificó la degradación del Nodo Norte en el segundo semestre.
- Las cifras se verificaron contra el archivo original antes de usarlas.
- Se generó el contenido de un informe ejecutivo, de una presentación y de una infografía sin requerir Copilot integrado en Office.

---

[⬅ Anterior: Práctica 6](../Practica06/README.md) | [Inicio](../../README.md) | [Siguiente: Práctica 8 ➡](../Practica08/README.md)
