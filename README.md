<p align="center">
  <img src="https://raw.githubusercontent.com/Netec-Mx/261108-Custom-IA-GEN-ESSE-DS-AB-Priv/main/assets/LogoNetec.png" alt="NETEC" width="180" />
</p>

# Inteligencia Artificial Generativa Essentials y Ciencia de datos aplicada

Este curso proporciona una introducción práctica al uso conjunto de la Inteligencia Artificial Generativa y los principios fundamentales de la Ciencia de Datos para el análisis e interpretación de grandes volúmenes de información. A lo largo del curso, los participantes aprenderán a utilizar herramientas como ChatGPT, Microsoft Copilot, Google Gemini y Claude para procesar documentos, analizar datos estructurados y no estructurados, identificar patrones e inconsistencias, y generar informes, reportes y documentos técnicos de manera más eficiente. Asimismo, conocerán las principales consideraciones relacionadas con la seguridad, la privacidad y el uso responsable de la Inteligencia Artificial en entornos institucionales.

## Accesos rápidos

- [**Setup Guide del curso**](https://github.com/Netec-Mx/261108-Custom-IA-GEN-ESSE-DS-AB-Priv/blob/main/SETUP_GUIDE.md)
- [Laboratorios por capítulo](#lista-de-laboratorios)

## Estructura

- `SETUP_GUIDE.md`: guía de instalación y preparación del entorno.
- `CapituloXX/README.md`: guía de laboratorio por capítulo.

## Lista de laboratorios

### Capítulo 3

- [Práctica: Implementar un proceso de verificación cruzada para validar la información generada por IA e identificar posibles inconsistencias antes de incorporarla a documentos institucionales.](Capitulo03/README.md#práctica-implementar-un-proceso-de-verificación-cruzada-para-validar-la-información-generada-por-ia-e-identificar-posibles-inconsistencias-antes-de-incorporarla-a-documentos-institucionales)
  - Descripción: El participante solicitará a una herramienta de IA Generativa un resumen o análisis a partir de un documento de referencia y contrastará cada afirmación relevante contra la fuente original y contra una segunda herramienta o fuente confiable. Registrará en una lista de verificación los datos confirmados, las imprecisiones, las posibles alucinaciones y los sesgos detectados, y documentará las correcciones necesarias antes de incorporar el contenido a un documento institucional. La práctica está planteada para realizarse con versiones gratuitas; el instructor podrá seleccionar la herramienta de IA Generativa más adecuada según su disponibilidad y límites de consumo, así como ajustar la profundidad, la complejidad y el volumen de datos, conservando el objetivo y el resultado esperado. Se recomienda utilizar información ficticia o previamente anonimizada.
  - Duración estimada: 10 min
- [Práctica: Implementación de protocolos de anonimización técnica e identificación de PII (Información de Identificación Personal) en grandes volúmenes de documentos antes de ser procesados por entornos de IA.](Capitulo03/README.md#práctica-implementación-de-protocolos-de-anonimización-técnica-e-identificación-de-pii-información-de-identificación-personal-en-grandes-volúmenes-de-documentos-antes-de-ser-procesados-por-entornos-de-ia)
  - Descripción: El participante revisará un conjunto de documentos de ejemplo para identificar datos de tipo PII, como nombres, domicilios, teléfonos, correos electrónicos e identificadores oficiales, y aplicará técnicas de anonimización como la sustitución por etiquetas, el enmascaramiento y la generalización. Posteriormente utilizará una herramienta de IA Generativa con los documentos ya anonimizados para comprobar que el análisis conserva su utilidad sin exponer información sensible, y documentará el protocolo aplicado para su reutilización. La práctica está planteada para realizarse con versiones gratuitas; el instructor podrá seleccionar la herramienta de IA Generativa más adecuada según su disponibilidad y límites de consumo, así como ajustar la profundidad, la complejidad y el volumen de datos, conservando el objetivo y el resultado esperado. Se recomienda utilizar información ficticia o previamente anonimizada.
  - Duración estimada: 10 min
  - [Ver capítulo completo](Capitulo03/README.md)

### Capítulo 4

- [Práctica: Diseñar prompts para resumir, clasificar, comparar y analizar grandes conjuntos de documentos relacionados con un mismo caso.](Capitulo04/README.md#práctica-diseñar-prompts-para-resumir-clasificar-comparar-y-analizar-grandes-conjuntos-de-documentos-relacionados-con-un-mismo-caso)
  - Descripción: El participante construirá prompts aplicando la estructura de rol, contexto, tarea, formato de salida y restricciones, e incorporará las técnicas Few-Shot y Chain of Thought para analizar un conjunto de documentos de un mismo caso. Elaborará un prompt para cada objetivo (resumir, clasificar, comparar y analizar), comparará los resultados obtenidos al refinar las instrucciones y conservará las versiones con salidas más consistentes como plantillas reutilizables. La práctica está planteada para realizarse con versiones gratuitas; el instructor podrá seleccionar la herramienta de IA Generativa más adecuada según su disponibilidad y límites de consumo, así como ajustar la profundidad, la complejidad y el volumen de datos, conservando el objetivo y el resultado esperado. Se recomienda utilizar información ficticia o previamente anonimizada.
  - Duración estimada: 13 min
- [Práctica: Diseñar prompts de control para forzar a la IA a auditar bases de datos textuales sin cometer errores de omisión.](Capitulo04/README.md#práctica-diseñar-prompts-de-control-para-forzar-a-la-ia-a-auditar-bases-de-datos-textuales-sin-cometer-errores-de-omisión)
  - Descripción: El participante diseñará prompts de control que indiquen a la IA recorrer todos los registros de una base de datos textual, numerar los elementos revisados, reportar explícitamente los registros sin hallazgos y contrastar el total procesado contra el total esperado. Evaluará los resultados con un conjunto de datos del que conozca de antemano los hallazgos, identificará las omisiones cometidas por la IA y ajustará las instrucciones hasta obtener una auditoría completa. La práctica está planteada para realizarse con versiones gratuitas; el instructor podrá seleccionar la herramienta de IA Generativa más adecuada según su disponibilidad y límites de consumo, así como ajustar la profundidad, la complejidad y el volumen de datos, conservando el objetivo y el resultado esperado. Se recomienda utilizar información ficticia o previamente anonimizada.
  - Duración estimada: 12 min
  - [Ver capítulo completo](Capitulo04/README.md)

### Capítulo 5

- [Práctica: Clasificación y categorización masiva de correspondencia, reportes o expedientes de la DPCI para la extracción automática de metadatos e indicadores estratégicos (KPIs).](Capitulo05/README.md#práctica-clasificación-y-categorización-masiva-de-correspondencia-reportes-o-expedientes-de-la-dpci-para-la-extracción-automática-de-metadatos-e-indicadores-estratégicos-kpis)
  - Descripción: El participante cargará a una herramienta de IA Generativa un conjunto de correspondencia, reportes o expedientes de ejemplo de la DPCI, previamente anonimizados, y definirá un esquema de categorías y de metadatos a extraer, como fecha, remitente, tipo de documento, tema y prioridad. Solicitará la clasificación de los documentos y la generación de una tabla consolidada en formato Excel, a partir de la cual identificará patrones, tendencias, anomalías e inconsistencias y calculará los KPIs más relevantes para el área. La práctica está planteada para realizarse con versiones gratuitas; el instructor podrá seleccionar la herramienta de IA Generativa más adecuada según su disponibilidad y límites de consumo, así como ajustar la profundidad, la complejidad y el volumen de datos, conservando el objetivo y el resultado esperado. Se recomienda utilizar información ficticia o previamente anonimizada.
  - Duración estimada: 30 min
  - [Ver capítulo completo](Capitulo05/README.md)

### Capítulo 6

- [Práctica: Prueba de rendimiento comparativa sometiendo a las distintas herramientas al análisis conjunto de un informe técnico extenso y su material visual asociado (gráficas o diagramas), evaluando su capacidad multimodal.](Capitulo06/README.md#práctica-prueba-de-rendimiento-comparativa-sometiendo-a-las-distintas-herramientas-al-análisis-conjunto-de-un-informe-técnico-extenso-y-su-material-visual-asociado-gráficas-o-diagramas-evaluando-su-capacidad-multimodal)
  - Descripción: El participante someterá un informe técnico extenso y su material visual asociado, como gráficas o diagramas, a varias herramientas de IA Generativa (por ejemplo ChatGPT, Copilot, Claude y Gemini) utilizando el mismo prompt en cada una. Evaluará los resultados en una matriz comparativa con criterios como precisión, comprensión de las gráficas, profundidad del análisis, formato de salida y límites de la versión utilizada, y concluirá qué herramienta conviene para cada tipo de tarea. La práctica está planteada para realizarse con versiones gratuitas; el instructor podrá seleccionar la herramienta de IA Generativa más adecuada según su disponibilidad y límites de consumo, así como ajustar la profundidad, la complejidad y el volumen de datos, conservando el objetivo y el resultado esperado. Se recomienda utilizar información ficticia o previamente anonimizada.
  - Duración estimada: 36 min
  - [Ver capítulo completo](Capitulo06/README.md)

### Capítulo 7

- [Práctica: Análisis automático de un archivo de Excel institucional con Copilot; generación de un informe ejecutivo estructurado en Word (objetivos, alcances, políticas, métricas y glosario) y creación automatizada de su presentación en PowerPoint.](Capitulo07/README.md#práctica-análisis-automático-de-un-archivo-de-excel-institucional-con-copilot-generación-de-un-informe-ejecutivo-estructurado-en-word-objetivos-alcances-políticas-métricas-y-glosario-y-creación-automatizada-de-su-presentación-en-powerpoint)
  - Descripción: El participante cargará un archivo de Excel institucional de ejemplo en Microsoft Copilot Chat y le solicitará el análisis de la información para identificar métricas, tendencias y hallazgos relevantes. A partir de ese análisis, pedirá a Copilot el contenido estructurado de un informe ejecutivo para Word con objetivos, alcances, políticas, métricas y glosario, y posteriormente la estructura de su presentación en PowerPoint, descargando los entregables generados por Copilot. La práctica se realiza con Microsoft Copilot Chat en su versión gratuita mediante la carga de archivos, sin requerir una licencia Premium ni la integración de Copilot dentro de las aplicaciones de Office; el instructor podrá simplificar el escenario o reducir el tamaño del archivo de acuerdo con los límites de la versión gratuita. Se recomienda utilizar información ficticia o previamente anonimizada.
  - Duración estimada: 36 min
  - [Ver capítulo completo](Capitulo07/README.md)

### Capítulo 8

- [Práctica: Uso avanzado de NotebookLM alimentado con el histórico de normativas, manuales y documentos generados por la DPCI para crear un repositorio inteligente de consulta rápida, síntesis profunda y redacción de materiales de capacitación.](Capitulo08/README.md#práctica-uso-avanzado-de-notebooklm-alimentado-con-el-histórico-de-normativas-manuales-y-documentos-generados-por-la-dpci-para-crear-un-repositorio-inteligente-de-consulta-rápida-síntesis-profunda-y-redacción-de-materiales-de-capacitación)
  - Descripción: El participante creará un cuaderno en NotebookLM y lo alimentará con un conjunto de normativas, manuales y documentos de ejemplo de la DPCI. Realizará consultas puntuales verificando las citas a las fuentes, generará síntesis comparativas entre documentos y utilizará las herramientas de NotebookLM, como guías de estudio, preguntas frecuentes y resúmenes, para redactar un material de capacitación sobre un tema normativo. La práctica debe realizarse con la herramienta indicada en el temario, ya que forma parte de los objetivos específicos de aprendizaje del módulo, utilizando su versión gratuita y considerando sus capacidades y limitaciones; el instructor podrá simplificar el escenario o utilizar conjuntos de datos más pequeños para que la actividad sea viable con los recursos disponibles. Se recomienda utilizar información ficticia o previamente anonimizada.
  - Duración estimada: 36 min
  - [Ver capítulo completo](Capitulo08/README.md)

### Capítulo 9

- [Práctica: Carga de una base de datos masiva de la DPCI para usar Advanced Data Analysis e identificar tendencias y anomalías, y uso de la interfaz Canvas para redactar, de forma iterativa y colaborativa, el documento oficial de conclusiones técnicas.](Capitulo09/README.md#práctica-carga-de-una-base-de-datos-masiva-de-la-dpci-para-usar-advanced-data-analysis-e-identificar-tendencias-y-anomalías-y-uso-de-la-interfaz-canvas-para-redactar-de-forma-iterativa-y-colaborativa-el-documento-oficial-de-conclusiones-técnicas)
  - Descripción: El participante cargará en ChatGPT una base de datos de ejemplo de la DPCI y utilizará Advanced Data Analysis para explorar la información, limpiar los datos, generar estadísticas descriptivas y gráficas, e identificar tendencias y anomalías. Con los hallazgos obtenidos, utilizará la interfaz Canvas para redactar y refinar de forma iterativa el documento oficial de conclusiones técnicas, solicitando ajustes de estructura, tono y nivel de detalle hasta obtener la versión final. La práctica debe realizarse con la herramienta indicada en el temario, ya que forma parte de los objetivos específicos de aprendizaje del módulo, utilizando su versión gratuita y considerando sus capacidades y limitaciones; el instructor podrá simplificar el escenario o utilizar conjuntos de datos más pequeños para que la actividad sea viable con los recursos disponibles. Se recomienda utilizar información ficticia o previamente anonimizada.
  - Duración estimada: 36 min
  - [Ver capítulo completo](Capitulo09/README.md)

### Capítulo 10

- [Práctica: Analizar un conjunto de documentos relacionados con un mismo expediente utilizando Claude para identificar hechos relevantes, detectar inconsistencias entre documentos y generar un informe técnico consolidado con evidencia y conclusiones.](Capitulo10/README.md#práctica-analizar-un-conjunto-de-documentos-relacionados-con-un-mismo-expediente-utilizando-claude-para-identificar-hechos-relevantes-detectar-inconsistencias-entre-documentos-y-generar-un-informe-técnico-consolidado-con-evidencia-y-conclusiones)
  - Descripción: El participante organizará en Claude los documentos de ejemplo de un mismo expediente, aprovechando su ventana de contexto y, cuando la versión disponible lo permita, un proyecto (Projects) con instrucciones y conocimiento del caso. Solicitará a Claude la identificación de hechos relevantes, la construcción de una línea de tiempo y la detección de inconsistencias entre documentos con referencia a la fuente de cada hallazgo, y finalmente generará un informe técnico consolidado con evidencia y conclusiones, verificando las citas contra los documentos originales. La práctica debe realizarse con la herramienta indicada en el temario, ya que forma parte de los objetivos específicos de aprendizaje del módulo, utilizando su versión gratuita y considerando sus capacidades y limitaciones; el instructor podrá simplificar el escenario o utilizar conjuntos de datos más pequeños para que la actividad sea viable con los recursos disponibles. Se recomienda utilizar información ficticia o previamente anonimizada.
  - Duración estimada: 36 min
  - [Ver capítulo completo](Capitulo10/README.md)

## Flujo de colaboración

- Trabajar en `changes_course`.
- Crear Pull Request hacia `main`.
- Merge por `Squash and merge`.

---

*Material didáctico preparado por Global K, S.A. de C.V.*
