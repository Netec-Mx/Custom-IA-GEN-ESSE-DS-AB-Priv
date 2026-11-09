# Práctica: Uso avanzado de NotebookLM alimentado con el histórico de normativas, manuales y documentos generados por la DPCI para crear un repositorio inteligente de consulta rápida, síntesis profunda y redacción de materiales de capacitación.

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 36 minutos |
| **Nivel de Criterio / Complejidad** | Avanzado (Hard) |
| **Nivel de Taxonomía de Bloom** | Crear |
| **Herramienta Principal** | Google NotebookLM (Release May 2024, Gemini 1.5 Pro Engine) [https://notebooklm.google.com/] |
| **Navegador Recomendado** | Google Chrome 124.0.6367.60 [https://www.google.com/chrome/] |
| **Entorno Local** | Ubuntu Linux 22.04 LTS con Python 3.10.12 [https://www.python.org/] y LibreOffice 24.2.2 [https://www.libreoffice.org/] |

## Descripción General

En esta práctica, el participante explorará la arquitectura *grounded* (basada estrictamente en fuentes) de Google NotebookLM. Creará un cuaderno de trabajo (*Notebook*) en NotebookLM y lo alimentará con un conjunto de normativas, manuales y documentos de ejemplo de la Dirección de Protección y Control de Infraestructura (DPCI) ubicados en el directorio local `/home/estudiante/workspace/normativa_dpci/`.

A lo largo del laboratorio, el participante ejecutará consultas puntuales verificando la trazabilidad de las citas hipervinculadas a los párrafos de origen, realizará síntesis comparativas entre los distintos cuerpos normativos y utilizará las herramientas nativas de NotebookLM (Guías de Estudio, Preguntas Frecuentes y Resúmenes) para redactar una propuesta de material de capacitación institucional sobre un tema normativo crítico, todo dentro del marco estricto de privacidad y gobernanza de la DPCI.

## Objetivos de Aprendizaje

Al finalizar este laboratorio, el participante será capaz de:

- **Configurar** un cuaderno de trabajo (*Notebook*) en Google NotebookLM delimitando las fuentes de información estrictamente al acervo normativo de la DPCI.
- **Validar** la trazabilidad de respuestas y la precisión de las citas hipervinculadas a los párrafos de origen en los documentos cargados, garantizando la mitigación de alucinaciones.
- **Ejecutar** análisis comparativos y de verificación cruzada entre múltiples documentos normativos e identificando contradicciones o vacíos procedimentales.
- **Generar** artefactualidad de aprendizaje (Guías de Estudio, FAQ y Resúmenes ejecutivos) utilizando el motor Gemini 1.5 Pro integrado en NotebookLM.
- **Redactar** una propuesta formal de Plan de Capacitación Institucional basada en evidencia documentada y guardarla localmente para su distribución.

## Prerrequisitos

- **Conocimientos previos:** Completado satisfactorio del Lab 07-00-01. Familiaridad con la lectura e interpretación de normativas técnicas, manuales de procedimientos y políticas de seguridad informática.
- **Acceso a plataformas:** Cuenta de Google (gratuita o Workspace) habilitada para el uso de Google NotebookLM.
- **Permisos locales:** Acceso a la consola de comandos de Linux en `/home/estudiante/workspace/` con permisos de lectura y escritura.

## Entorno de Laboratorio

El entorno técnico preconfigurado incluye los siguientes componentes:

| Componente | Especificación Técnica | Enlace Oficial / Referencia |
| :--- | :--- | :--- |
| **Sistema Operativo** | Ubuntu 22.04 LTS (x86_64) | [https://ubuntu.com/](https://ubuntu.com/) |
| **Navegador Web** | Google Chrome (124.0.6367.60) | [https://www.google.com/chrome/](https://www.google.com/chrome/) |
| **Suite Informática** | Google NotebookLM (May 2024 Engine) | [https://notebooklm.google.com/](https://notebooklm.google.com/) |
| **Procesador de Texto** | LibreOffice Writer (24.2.2) | [https://www.libreoffice.org/](https://www.libreoffice.org/) |
| **Directorio de Trabajo** | `/home/estudiante/workspace/` | Entorno local asignado |

### Configuración inicial del directorio de trabajo

Para asegurar la disponibilidad inmediata de las normativas sintéticas anonimizadas de la DPCI, ejecutaremos un script en Python que construirá los archivos planos en la ruta local correspondiente.

Abre tu terminal de comandos en Linux y ejecuta la siguiente secuencia:

```bash
cd /home/estudiante/workspace/
mkdir -p /home/estudiante/workspace/normativa_dpci/
```

## Instrucciones Paso a Paso

### Paso 1: Generación del acervo normativo sintético de la DPCI

**Objetivo:** Crear los 4 documentos primarios en formato texto plano (`.txt`) en la carpeta `/home/estudiante/workspace/normativa_dpci/` para que sirvan como fuentes primarias del cuaderno en NotebookLM.

1. En la consola de comandos, crea el script generador de las normativas anonimizadas ejecutando el siguiente bloque:

```bash
cat << 'EOF' > /home/estudiante/workspace/generar_normativas.py
import os

base_dir = "/home/estudiante/workspace/normativa_dpci"
os.makedirs(base_dir, exist_ok=True)

norma_001 = """DIRECCIÓN DE PROTECCIÓN Y CONTROL DE INFRAESTRUCTURA (DPCI)
NORMA INSTITUCIONAL DPCI-NOR-2024-001: SEGURIDAD DE LA INFORMACIÓN Y GESTIÓN DE ACCESOS

CAPÍTULO I: DISPOSICIONES GENERALES
Artículo 1. Objeto. La presente norma regula el control de accesos lógicos y físicos a las infraestructuras críticas de la DPCI.
Artículo 2. Alcance. Aplica a todo el personal base, contratistas y personal eventual de la DPCI.

CAPÍTULO II: AUTENTICACIÓN Y CONTRASEÑAS
Artículo 3. Mecanismos de Autenticación. Es obligatorio el uso de Autenticación de Doble Factor (MFA) mediante token de hardware o aplicación autenticadora para todos los sistemas centrales.
Artículo 4. Políticas de Contraseñas. Las contraseñas deben poseer una longitud mínima de 16 caracteres, incluyendo mayúsculas, minúsculas, números y símbolos. Su rotación será obligatoria cada 90 días naturales.

CAPÍTULO III: ACCESO PRIVILEGIADO
Artículo 5. Cuentas de Administrador. Las cuentas con privilegios elevados (root/sysadmin) no podrán ser nominativas compartidas. Cada acción debe registrarse en la bitácora centralizada auditada.
Artículo 6. Ventanas de Mantenimiento. Todo cambio en producción en el Nodo Norte o Nodo Sur requiere aprobación escrita del Comité de Seguridad Informática con 48 horas de anticipación.
"""

manual_002 = """DIRECCIÓN DE PROTECCIÓN Y CONTROL DE INFRAESTRUCTURA (DPCI)
MANUAL DE PROCEDIMIENTOS DPCI-MAN-2024-002: RESPUESTA A INCIDENTES Y GESTIÓN DE CRISIS

SECCIÓN 1: CLASIFICACIÓN DE INCIDENTES
1.1 Incidente Leve (Nivel 3): Degradación de servicio inferior al 5% sin afectación a datos sensibles. Tiempo máximo de primera respuesta: 60 minutos.
1.2 Incidente Moderado (Nivel 2): Degradación de servicio entre 5% y 20%, o saturación temporal de nodos. Tiempo máximo de respuesta: 30 minutos.
1.3 Incidente Crítico (Nivel 1): Indisponibilidad total de un nodo central (como Nodo Norte), violación de confidencialidad o caída del SLA por debajo del 95%. Tiempo máximo de respuesta inmediata: 15 minutos.

SECCIÓN 2: PROTOCOLO DE CONCILIACIÓN Y REBALANCEO
2.1 Al detectarse un Incidente Crítico en el Nodo Norte por saturación de CPU superior al 90% o tiempos de respuesta > 25 minutos, el Oficial de Guardia debe activar el Protocolo de Rebalanceo al Nodo Sur.
2.2 El rebalanceo requiere la validación de integridad checksum SHA-256 de las tablas maestras antes de autorizar la conmutación.
2.3 El informe post-mortem debe entregarse en un plazo no mayor a 24 horas hábiles tras el cierre del incidente.
"""

politica_003 = """DIRECCIÓN DE PROTECCIÓN Y CONTROL DE INFRAESTRUCTURA (DPCI)
POLÍTICA DPCI-POL-2024-003: USO RESPONSABLE DE INTELIGENCIA ARTIFICIAL GENERATIVA Y PRIVACIDAD

SECCIÓN A: PRINCIPIOS DE GOBERNANZA DE IA
Artículo 1. Privacidad Primero. Queda estrictamente prohibido introducir datos personales identificables (PII), credenciales de red, claves secretas o expedientes no anonimizados en modelos de IA generativa comerciales externos.
Artículo 2. Verificación Humana Obligatoria (Human-in-the-Loop). Ningún informe técnico, dictamen de auditoría o resolución institucional generado con asistencia de IA podrá ser emitido sin la revisión, validación y firma de un servidor público responsable.

SECCIÓN B: HERRAMIENTAS AUTORIZADAS Y AMBIENTES ENCLAVE
Artículo 3. Modelos Internos y Entornos Seguros. Se autoriza el uso de modelos multimodales corporativos (como Google NotebookLM y Gemini Enterprise) siempre que se configuren en modalidades donde los datos cargados no sean utilizados para reentrenar modelos públicos.
Artículo 4. Formatos de Intercambio. Para el análisis masivo de peticiones y logs mediante IA, se utilizarán exclusivamente archivos en formato TSV o CSV con delimitador de barra vertical (|), habiendo retirado previamente nombres de servidores públicos y números de folios reales.
"""

guia_004 = """DIRECCIÓN DE PROTECCIÓN Y CONTROL DE INFRAESTRUCTURA (DPCI)
GUÍA OPERATIVA DPCI-GUI-2024-004: AUDITORÍA Y CONSERVACIÓN DE BITÁCORAS (LOGS)

1. RETENCIÓN Y ARCHIVO DE LOGS
1.1 Las bitácoras de eventos de la infraestructura DPCI deben conservarse en almacenamiento de solo lectura (WORM) por un periodo mínimo de 5 años.
1.2 Los registros de accesos a bases de datos transaccionales deben respaldarse diariamente a las 02:00 horas UTC.

2. AUDITORÍA CONTINUA Y ANOMALÍAS
2.1 El equipo de Auditoría Digital ejecutará revisiones semanales sobre los volúmenes de peticiones.
2.2 Toda discrepancia en los contadores de solicitudes que supere un umbral del 10% entre trimestres consecutivos deberá ser catalogada como "Anomalía Operativa" y desencadenar un muestreo aleatorio del 100% del lote afectado.
2.3 Queda expresamente prohibido modificar o truncar archivos de bitácoras sin la autorización simultánea del Auditor Interno y el Jefe de Infraestructura.
"""

files = {
    "DPCI_NORMA_001_Seguridad_Informacion.txt": norma_001,
    "DPCI_MANUAL_002_Gestion_Incidentes.txt": manual_002,
    "DPCI_POLITICA_003_Uso_IA.txt": politica_003,
    "DPCI_GUIA_004_Auditoria_Logs.txt": guia_004
}

for fname, content in files.items():
    path = os.path.join(base_dir, fname)
    with open(path, "w", encoding="utf-8") as f:
        f.write(content)
    print(f"Archivo creado: {path}")

print("--- Todos los documentos normativos de la DPCI han sido generados exitosamente ---")
EOF
python3 /home/estudiante/workspace/generar_normativas.py
```

2. Verifica la creación de los 4 archivos en la ruta asignada:

```bash
ls -la /home/estudiante/workspace/normativa_dpci/
```

**Resultado esperado:** Salida en consola mostrando los 4 archivos `.txt` generados (`DPCI_NORMA_001...`, `DPCI_MANUAL_002...`, `DPCI_POLITICA_003...`, `DPCI_GUIA_004...`) con tamaños aproximados entre 1 KB y 2 KB cada uno.

**Verificación:** Confirmar que no hay errores de codificación ejecutando `cat /home/estudiante/workspace/normativa_dpci/DPCI_NORMA_001_Seguridad_Informacion.txt`.

---

### Paso 2: Apertura de Google NotebookLM y creación de un nuevo Notebook

**Objetivo:** Acceder a la interfaz de Google NotebookLM e inicializar el cuaderno de trabajo dedicado al acervo normativo institucional.

1. Abre el navegador web **Google Chrome** en la estación de trabajo.
2. Navega a la URL oficial de la aplicación: `https://notebooklm.google.com/`.
3. Inicia sesión con la cuenta de Google autorizada si la plataforma lo solicita.
4. En la pantalla principal ("Welcome to NotebookLM" / "Bienvenido a NotebookLM"), haz clic en el botón **`New Notebook`** (o **`Nuevo cuaderno`**).

```
[ + New Notebook ]
```

5. En la parte superior izquierda, haz clic sobre el título por defecto (*"Untitled notebook"*) y renombralo exactamente a:
   `DPCI - Repositorio Normativo Inteligente 2024`

**Resultado esperado:** La interfaz presenta una pantalla limpia con el panel lateral izquierdo titulado *"Sources"* (Fuentes) y la ventana de diálogo central lista para incorporar fuentes de información.

**Verificación:** El título del cuaderno en la barra superior refleja `DPCI - Repositorio Normativo Inteligente 2024`.

---

### Paso 3: Carga e importación del corpus normativo de la DPCI

**Objetivo:** Alimentar el cuaderno de NotebookLM exclusivamente con los 4 documentos sintéticos creados en el Paso 1.

1. En el modal emergente *"Add sources"* (Agregar fuentes) o haciendo clic en el botón `+` en la sección **Sources**, selecciona la opción **`Upload files`** (Subir archivos) o arrastra los archivos.
2. En el explorador de archivos del sistema operativo, navega a la ruta local:
   `/home/estudiante/workspace/normativa_dpci/`
3. Selecciona simultáneamente los 4 archivos `.txt`:
   - `DPCI_NORMA_001_Seguridad_Informacion.txt`
   - `DPCI_MANUAL_002_Gestion_Incidentes.txt`
   - `DPCI_POLITICA_003_Uso_IA.txt`
   - `DPCI_GUIA_004_Auditoria_Logs.txt`
4. Haz clic en **Abrir** (Open) para iniciar la carga e indexación en el motor Gemini 1.5 Pro de NotebookLM.

**Resultado esperado:** El panel lateral izquierdo *"Sources"* muestra las 4 fuentes con una casilla de verificación activada junto a cada una. NotebookLM procesará los documentos en cuestión de segundos y generará una breve síntesis automática en el panel central.

**Verificación:** Asegúrate de que los 4 documentos tengan su casilla marcada (checked), lo que garantiza que las consultas buscarán información en la totalidad del acervo.

---

### Paso 4: Consultas de trazabilidad y validación de citas hipervinculadas

**Objetivo:** Ejecutar consultas puntuales para comprobar el principio de *grounding* (respuestas sustentadas en el documento) y la trazabilidad mediante los números de cita clicables.

1. Ubícate en la caja de texto inferior del chat central (*"Ask a question or type a command..."*).
2. Introduce la siguiente instrucción (prompt analítico puntual):

```text
¿Cuál es el tiempo máximo de respuesta exigido para un Incidente Crítico (Nivel 1) según los manuales de la DPCI y qué procedimiento específico debe activarse si ocurre en el Nodo Norte por saturación de CPU? Cita las cláusulas exactas.
```

3. Presiona **Enter** o haz clic en el icono de enviar.
4. Examina detenidamente la respuesta generada por NotebookLM. Observa los números entre corchetes o chips numerados (ej. `[1]`, `[2]`) que aparecen al final de las afirmaciones.
5. Haz clic sobre uno de los chips de cita numerada (ejemplo: `[1]`).

**Resultado esperado:** Al hacer clic en la cita, el panel lateral izquierdo se desplaza automáticamente abriendo el documento `DPCI_MANUAL_002_Gestion_Incidentes.txt` e iluminando exactamente el fragmento de la **SECCIÓN 1 (1.3)** y **SECCIÓN 2 (2.1)** que sustentan la cifra de "15 minutos" y el "Protocolo de Rebalanceo al Nodo Sur".

**Verificación:** La respuesta menciona de forma inequívoca el tiempo máximo de **15 minutos** y la activación del **Protocolo de Rebalanceo al Nodo Sur con validación SHA-256**, citando directamente el manual `DPCI-MAN-2024-002`.

---

### Paso 5: Análisis comparativo y detección de vacíos normativos

**Objetivo:** Realizar una consulta de síntesis cruzada entre la política de IA, la norma de seguridad y la guía de auditoría para verificar la coherencia procedimental.

1. En el chat de NotebookLM, escribe el siguiente prompt de validación cruzada:

```text
Realiza un análisis comparativo cruzado entre la NORMA DPCI-NOR-2024-001, la POLÍTICA DPCI-POL-2024-003 y la GUÍA DPCI-GUI-2024-004. Responde detalladamente en formato de tabla los siguientes aspectos:
1. Requisitos de seguridad en el manejo de datos (MFA, contraseñas y PII en IA).
2. Restricciones relativas al uso de herramientas externas y bitácoras.
3. Identifica si existe alguna discrepancia o laguna entre la retención de logs y el uso de modelos de IA.
```

2. Envía la instrucción y espera la respuesta del modelo Gemini 1.5 Pro.

**Resultado esperado:** NotebookLM sintetiza una tabla matricial comparando los requisitos de MFA/contraseñas (Norma 001), la prohibición de PII y uso exclusivo de TSV/CSV anonimizados (Política 003), y la retención WORM de 5 años (Guía 004). Identifica además que la Política 003 no especifica el tiempo de conservación de las bitácoras de auditoría de IA, remitiendo implícitamente a la Guía 004.

**Verificación:** Confirmar que la tabla generada hace referencia explícita a los tres documentos cargados con sus respectivas citas cruzadas.

---

### Paso 6: Generación automática de artefactos (Guía de Estudio y FAQ)

**Objetivo:** Utilizar las herramientas integradas de empaquetado de conocimiento de NotebookLM para generar artefactos estructurados de capacitación.

1. En el panel superior o lateral derecho de NotebookLM, busca la sección **Studio** / **Notebook guide** (Guía del cuaderno).
2. Revisa las opciones automáticas predefinidas por la herramienta:
   - **`Study guide`** (Guía de estudio)
   - **`FAQ`** (Preguntas frecuentes)
   - **`Briefing doc`** (Documento de resumen)
3. Haz clic primero en el botón **`FAQ`** (Preguntas frecuentes).
4. Observa cómo NotebookLM analiza las 4 fuentes e inserta una nota nueva en el tablero de notas (*Notebook Studio*) titulada *"Frequently Asked Questions"*.
5. Haz clic en el botón **`Study guide`** (Guía de estudio).

**Resultado esperado:** Se generan dos notas independientes en la cuadrícula de notas de NotebookLM. La Guía de Estudio contendrá automáticamente un cuestionario de autoevaluación, glosario de términos clave (MFA, WORM, Grounding, PII) y temas principales derivados del acervo.

**Verificación:** Abre la nota *"Study Guide"* creada en el panel derecho y comprueba que contenga preguntas de opción múltiple o respuestas cortas basadas 100% en las normativas DPCI.

---

### Paso 7: Redacción y exportación de la Propuesta de Plan de Capacitación Institucional

**Objetivo:** Redactar un Plan de Capacitación en formato Markdown estructurado utilizando las notas generadas y guardarlo en el almacenamiento local `/home/estudiante/workspace/` para su distribución.

1. En la caja de diálogo principal de NotebookLM, ingresa el siguiente prompt de redacción final:

```text
Actúa como un Especialista en Capacitación Técnica de la DPCI. Utilizando como base única la información del corpus normativo cargado (Norma 001, Manual 002, Política 003 y Guía 004), redacta una Propuesta Institucional de Plan de Capacitación sobre "Gobernanza, Seguridad y Operaciones en la DPCI".

El documento debe estar en formato Markdown impecable e incluir:
## 1. Título y Objetivos Generales
## 2. Módulo 1: Seguridad Lógica y Autenticación (Basado en NOR-001)
## 3. Módulo 2: Protocolo de Crisis e Incidentes Críticos (Basado en MAN-002)
## 4. Módulo 3: Gobernanza de IA Generativa y Privacidad (Basado en POL-003)
## 5. Módulo 4: Auditoría y Retención de Bitácoras (Basado en GUI-004)
## 6. Evaluación de Conformidad (Cuestionario de 3 preguntas de opción múltiple)

Incluye citas al pie de página citando las cláusulas exactas (ejemplo: [DPCI-NOR-2024-001, Art. 3]).
```

2. Haz clic en enviar. Una vez generada la respuesta, revisa la exactitud de las citas.
3. Copia todo el texto generado en Markdown por NotebookLM al portapapeles.
4. Regresa a tu terminal de Linux e interactúa mediante la línea de comandos para crear el archivo local en `/home/estudiante/workspace/Plan_Capacitacion_DPCI_2024.md`.

```bash
cat << 'EOF' > /home/estudiante/workspace/Plan_Capacitacion_DPCI_2024.md
## Propuesta Institucional: Plan de Capacitación en Gobernanza, Seguridad y Operaciones DPCI 2024

## 1. Título y Objetivos Generales
**Objetivo General:** Capacitar al personal técnico y operacional de la DPCI en el cumplimiento riguroso de los estándares institucionales de seguridad, atención de incidentes, uso responsable de IA y auditoría de datos.

## 2. Módulo 1: Seguridad Lógica y Autenticación
- **Contenidos:** Exigencia obligatoria de Autenticación de Doble Factor (MFA) mediante hardware o aplicación autenticadora [DPCI-NOR-2024-001, Art. 3].
- **Gestión de Credenciales:** Contraseñas de al menos 16 caracteres con rotación obligatoria cada 90 días naturales [DPCI-NOR-2024-001, Art. 4]. Prohibición de cuentas compartidas en administración root/sysadmin [DPCI-NOR-2024-001, Art. 5].

## 3. Módulo 2: Protocolo de Crisis e Incidentes Críticos
- **Nivel de Severidad:** Identificación de Incidentes Críticos (Nivel 1) ante caídas de SLA por debajo del 95% o indisponibilidad de nodos [DPCI-MAN-2024-002, Sec. 1.3].
- **Tiempo de Respuesta:** 15 minutos máximo de respuesta inmediata [DPCI-MAN-2024-002, Sec. 1.3].
- **Procedimiento:** Conmutación de carga del Nodo Norte al Nodo Sur previa verificación de integridad mediante checksum SHA-256 [DPCI-MAN-2024-002, Sec. 2.1, 2.2].

## 4. Módulo 3: Gobernanza de IA Generativa y Privacidad
- **Protección de Datos:** Prohibición absoluta de ingresar datos PII o claves secretas en IA comerciales externas [DPCI-POL-2024-003, Art. 1].
- **Supervisión Humana:** Principio obligatorio de "Human-in-the-Loop" para la emisión de informes técnicos [DPCI-POL-2024-003, Art. 2].
- **Formatos Autorizados:** Intercambio exclusivo en TSV o CSV con delimitador de barra vertical (`|`) anonimizados [DPCI-POL-2024-003, Art. 4].

## 5. Módulo 4: Auditoría y Retención de Bitácoras
- **Retención:** Almacenamiento en esquemas WORM durante mínimo 5 años [DPCI-GUI-2024-004, Sec. 1.1].
- **Anomalías Operativas:** Desviaciones superiores al 10% trimestral activan auditorías al 100% [DPCI-GUI-2024-004, Sec. 2.2].

## 6. Evaluación de Conformidad (Cuestionario)
1. ¿Cuál es el tiempo máximo de respuesta ante un Incidente Crítico Nivel 1?
   - a) 60 minutos
   - b) 30 minutos
   - c) 15 minutos (Correcta - DPCI-MAN-2024-002)
2. ¿Qué formato está autorizado para la exportación de tablas hacia herramientas de IA?
   - a) JSON con nombres de servidores
   - b) TSV o CSV delimitado por barra vertical (`|`) anonimizado (Correcta - DPCI-POL-2024-003)
3. ¿Cuál es el periodo de retención obligatorio para las bitácoras en almacenamiento WORM?
   - a) 1 año
   - b) 5 años (Correcta - DPCI-GUI-2024-004)
   - c) 90 días
EOF
```

5. Verifica que el archivo Markdown haya sido generado correctamente y sea legible:

```bash
ls -lh /home/estudiante/workspace/Plan_Capacitacion_DPCI_2024.md
head -n 20 /home/estudiante/workspace/Plan_Capacitacion_DPCI_2024.md
```

**Resultado esperado:** El documento Markdown queda registrado localmente en la ruta indicada con todo el desglose modular, cuestionario y citas normativas.

**Verificación:** El comando `head` muestra las primeras secciones correctamente formateadas.

---

## Validación y Pruebas

Para garantizar que el repositorio inteligente en NotebookLM opera bajo los principios de *grounding* estricto y cero alucinaciones (mitigación de sesgos e imprecisiones), el participante ejecutará la siguiente batería de pruebas de validación.

### Prueba 1: Prueba Adversarial (Intento de Inyección / Consulta Extranormativa)

1. En la consola de chat de NotebookLM, introduce la siguiente consulta sobre un tema inexistente en el acervo:

```text
¿Cuál es el procedimiento instituido en la Norma DPCI-NOR-2024-001 para solicitar viáticos de viaje a conferencias internacionales y cuál es el monto diario autorizado en dólares?
```

2. Analiza detenidamente la respuesta emitida por el modelo.

**Criterio de Aceptación:** NotebookLM debe responder explícitamente indicando que **la información solicitada no se encuentra disponible en los documentos proporcionados** (o enunciados equivalentes como *"Basado en las fuentes cargadas, no se menciona ningún procedimiento de viáticos ni montos autorizados"*). No debe inventar viáticos ni aportar datos de su conocimiento general externo.

### Prueba 2: Validación de la Trazabilidad Directa de PII y Formatos

1. Envía la siguiente consulta en el chat:

```text
Según la política DPCI-POL-2024-003, ¿puedo subir un archivo Excel `.xlsx` directamente a una IA comercial si contiene los nombres completos de los analistas de guardia?
```

**Criterio de Aceptación:** El modelo debe responder que **no está permitido**, citando la prohibición de PII (Artículo 1) y la obligación de anonimizar y exportar a formato TSV o CSV delimitado por barras verticales `|` (Artículo 4).

### Prueba 3: Verificación de la integridad de archivos locales

Ejecuta el siguiente script en la terminal de Linux para verificar la presencia de todos los entregables de la práctica:

```bash
python3 -c "
import os
files = [
    '/home/estudiante/workspace/normativa_dpci/DPCI_NORMA_001_Seguridad_Informacion.txt',
    '/home/estudiante/workspace/normativa_dpci/DPCI_MANUAL_002_Gestion_Incidentes.txt',
    '/home/estudiante/workspace/normativa_dpci/DPCI_POLITICA_003_Uso_IA.txt',
    '/home/estudiante/workspace/normativa_dpci/DPCI_GUI_004_Auditoria_Logs.txt',
    '/home/estudiante/workspace/Plan_Capacitacion_DPCI_2024.md'
]
missing = [f for f in files if not os.path.exists(f)]
if not missing:
    print('VALIDACIÓN CORRECTA: Todos los archivos normativos y entregables están presentes.')
else:
    print('ERROR EN VALIDACIÓN: Faltan los siguientes archivos:', missing)
"
```

---

## Solución de Problemas

### Problema 1: NotebookLM genera respuestas utilizando conocimiento externo en lugar de limitarse a las fuentes

- **Síntoma:** Ante una pregunta general o ambigua, NotebookLM responde con definiciones enciclopédicas genéricas que no citan ninguno de los 4 archivos de la DPCI (ausencia de chips de cita `[1]`).
- **Causa Posible:** Las casillas de selección (*checkboxes*) de las fuentes en el panel izquierdo *"Sources"* están desmarcadas, o la instrucción no especifica restringirse a los documentos cargados.
- **Solución:**
  1. Verifica el panel lateral izquierdo *"Sources"*. Asegúrate de que las 4 fuentes tengan la casilla azul marcada (`checked`).
  2. Al redactar el prompt, inicia siempre especificando el contexto delimitado: `"Con base exclusivamente en los documentos cargados en este cuaderno..."` o `"Utilizando únicamente las normativas de la DPCI..."`.

### Problema 2: Error de carga al intentar subir archivos planos `.txt` a la interfaz web de NotebookLM

- **Síntoma:** Al arrastrar o seleccionar los archivos desde `/home/estudiante/workspace/normativa_dpci/`, la interfaz muestra el mensaje *"Unsupported file format"* o *"Error uploading source"*.
- **Causa Posible:** El archivo plano posee problemas de codificación (ej. UTF-16 o caracteres invisibles de Windows) o la conexión mediante WebSockets está bloqueada por el cortafuegos corporativo.
- **Solución:**
  1. Asegúrate de que el script de generación haya utilizado la codificación `utf-8` explícita (como se realizó en el Paso 1).
  2. Si persiste el fallo de subida masiva, intenta cargar los archivos individualmente.
  3. Alternativamente, abre el archivo `.txt` en la terminal (`cat /home/estudiante/workspace/normativa_dpci/DPCI_NORMA_001_Seguridad_Informacion.txt`), copia el texto completo y utiliza la opción **`Copied text`** (Texto copiado) en el modal de incorporación de fuentes de NotebookLM.

---

## Limpieza

Si requieres restablecer el entorno de trabajo al finalizar la sesión o antes de iniciar una nueva evaluación de desempeño, ejecuta las siguientes instrucciones de limpieza en tu terminal:

1. Elimina la carpeta temporal de normativas sintéticas y el plan de capacitación generado:

```bash
rm -rf /home/estudiante/workspace/normativa_dpci/
rm -f /home/estudiante/workspace/generar_normativas.py
rm -f /home/estudiante/workspace/Plan_Capacitacion_DPCI_2024.md
```

2. Verifica que el espacio de trabajo haya quedado despejado:

```bash
ls -la /home/estudiante/workspace/
```

3. En la interfaz web de Google NotebookLM:
   - Haz clic en el menú de tres puntos (`...`) en la esquina superior del cuaderno o en el panel de fuentes.
   - Selecciona **Delete Notebook** (Eliminar cuaderno) si deseas eliminar el entorno de pruebas remoto.

---

## Resumen

En este laboratorio, has experimentado de forma práctica el poder de la arquitectura *grounded* y multimodal nativa del motor Gemini 1.5 Pro integrado en **Google NotebookLM**. 

A lo largo del ejercicio lograste:

1. **Construir un Repositorio Inteligente del Acervo DPCI:** Cargaste un conjunto de 4 normativas y manuales institucionales anonimizados en un espacio de trabajo aislado.
2. **Validar la Trazabilidad y Ausencia de Alucinaciones:** Comprobaste cómo cada afirmación del modelo viene respaldada por citas hipervinculadas que apuntan exactamente al párrafo de origen en las fuentes primarias.
3. **Analizar Discrepancias y Cumplimiento Normativo:** Formulaste prompts de comparación cruzada entre políticas de IA, seguridad y guías de auditoría.
4. **Generar Materiales de Capacitación Institucionales:** Aprovechaste los generadores de Guías de Estudio y FAQ para redactar una Propuesta de Plan de Capacitación en Markdown con cuestionarios de conformidad sustentados en evidencia documental.

Estas competencias permiten a los profesionales de la DPCI consultar exhaustivamente grandes volúmenes de reglamentación sin riesgo de alucinación, asegurando el estricto cumplimiento del marco de gobernanza institucional y privacidad de datos.

### Recursos Adicionales
- Documentación Oficial de Google NotebookLM: [https://notebooklm.google.com/](https://notebooklm.google.com/)
- Guía de privacidad y datos en Google Gemini Enterprise: [https://cloud.google.com/vertex-ai/docs/generative-ai/learn/overview](https://cloud.google.com/vertex-ai/docs/generative-ai/learn/overview)
