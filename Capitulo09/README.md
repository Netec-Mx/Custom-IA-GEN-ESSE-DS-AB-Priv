# Práctica: Carga de una base de datos masiva de la DPCI para usar Advanced Data Analysis e identificar tendencias y anomalías, y uso de la interfaz Canvas para redactar, de forma iterativa y colaborativa, el documento oficial de conclusiones técnicas.

## Metadatos

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 36 minutos |
| **Complejidad** | Avanzada (Hard) |
| **Nivel de Bloom** | Crear |

## Descripción General

En este laboratorio práctico, el participante utilizará las herramientas avanzadas de ChatGPT (Advanced Data Analysis y la interfaz interactiva Canvas) para procesar un conjunto masivo de datos de solicitudes de servicio anonimizadas de la Dirección de Protección y Control de Infraestructura (DPCI). El participante ejecutará un análisis exploratorio de datos (EDA), identificará tendencias y valores atípicos mediante el procesamiento asistido por Python en segundo plano, y generará gráficos descriptivos. Posteriormente, migrará el flujo de trabajo hacia la interfaz Canvas para redactar, estructurar y refinarel informe técnico oficial de conclusiones en un entorno iterativo y colaborativo de interacción hombre-máquina, cumpliendo con los estándares de privacidad institucionales.

## Objetivos de Aprendizaje

Al finalizar este laboratorio, el participante será capaz de:

- [ ] Generar y validar el conjunto de datos sintético anonimizado de la DPCI (`dpci_dataset_2024.csv`) en la ruta de trabajo local.
- [ ] Cargar e interactuar con datos masivos en ChatGPT utilizando Advanced Data Analysis para depurar valores nulos, calcular estadísticas descriptivas e identificar anomalías operativas.
- [ ] Interpretar y solicitar gráficos cuantitativos (histogramas de distribución de tiempos y diagramas de dispersión de carga de trabajo) sin necesidad de escribir código manual.
- [ ] Utilizar la interfaz Canvas de ChatGPT para redactar y modificar colaborativamente el documento oficial de conclusiones técnicas, ajustando tono, estructura y nivel de detalle.
- [ ] Aplicar verificaciones cruzadas entre los hallazgos cuantitativos de Advanced Data Analysis y el texto generado en Canvas para mitigar alucinaciones y sesgos.

## Prerrequisitos

- **Conocimientos previos:** Finalización de los laboratorios 06 a 08. Nociones fundamentales de estadística descriptiva (promedio, mediana, desviación estándar y valores atípicos).
- **Herramientas y Software:**
  - Navegador Web Google Chrome versión 124.0.6367.60 ([https://www.google.com/chrome/](https://www.google.com/chrome/)) o Microsoft Edge versión 124.0.2478.67 ([https://www.microsoft.com/edge](https://www.microsoft.com/edge)).
  - Acceso a la interfaz web de ChatGPT (Build May 2024 Web App) con funciones de Advanced Data Analysis y Canvas habilitadas ([https://chatgpt.com/](https://chatgpt.com/)).
  - Python versión 3.10.12 ([https://www.python.org/](https://www.python.org/)) instalado en el entorno local para la generación del dataset sintético.

## Entorno de Laboratorio

### Especificaciones del Entorno

| Componente | Especificación |
| :--- | :--- |
| **Sistema Operativo Base** | Ubuntu 22.04 LTS (o equivalente en contenedor Linux / entorno de trabajo local) |
| **Ruta de Trabajo Principal** | `/home/estudiante/workspace/` |
| **Archivo de Datos Principal** | `/home/estudiante/workspace/dpci_dataset_2024.csv` |
| **Navegador Obligatorio** | Google Chrome 124.0.6367.60 o Microsoft Edge 124.0.2478.67 |
| **Modelo de LLM Principal** | ChatGPT (GPT-4o con Canvas y Advanced Data Analysis) |
| **Modelo de Respaldo** | Google Gemini 1.5 Flash ([https://gemini.google.com/](https://gemini.google.com/)) |

### Configuración del Espacio de Trabajo

Ejecute los siguientes comandos en la terminal local para asegurar la disponibilidad del directorio de trabajo y generar el dataset sintético anonimizado de más de 5,000 registros para la DPCI.

```bash
cd /home/estudiante/workspace/
cat << 'EOF' > /home/estudiante/workspace/generar_dataset_dpci.py
import csv
import random
from datetime import datetime, timedelta

random.seed(42)
n_records = 5200

nodos = ['Nodo_Norte', 'Nodo_Sur', 'Nodo_Central', 'Nodo_Occidente']
tipos_solicitud = ['Mantenimiento_Preventivo', 'Incidente_Critico', 'Actualizacion_Software', 'Auditoria_Acceso', 'Soporte_Usuario']
estados = ['Cerrado', 'Pendiente', 'En_Proceso', 'Escalado']

start_date = datetime(2024, 1, 1)

with open('/home/estudiante/workspace/dpci_dataset_2024.csv', mode='w', newline='', encoding='utf-8') as f:
    writer = csv.writer(f)
    writer.writerow(['ID_Solicitud', 'Fecha_Creacion', 'Nodo_Infraestructura', 'Tipo_Solicitud', 'Tiempo_Respuesta_Min', 'Horas_Recurso', 'Estado', 'Puntaje_Prioridad'])
    
    for i in range(1, n_records + 1):
        id_sol = f"REQ-DPCI-2024-{i:05d}"
        fecha = start_date + timedelta(minutes=random.randint(0, 200000))
        nodo = random.choice(nodos)
        tipo = random.choice(tipos_solicitud)
        
        # Introducción de distribución normal con sesgo y atípicos
        if tipo == 'Incidente_Critico' and nodo == 'Nodo_Norte':
            # Anomalía inyectada: Nodo Norte en incidentes críticos presenta tiempos anormalmente altos
            tiempo_resp = round(random.normalvariate(180, 45), 2)
            if random.random() < 0.05: # Atípico extremo
                tiempo_resp = round(random.uniform(500, 950), 2)
        else:
            tiempo_resp = round(random.normalvariate(35, 12), 2)
        
        tiempo_resp = max(1.0, tiempo_resp) # Evitar valores negativos
        
        # Introducción de valores nulos intencionales (1.5% de los datos) para probar depuración
        horas_rec = round(random.uniform(0.5, 40.0), 1) if random.random() > 0.015 else ""
        estado = random.choice(estados)
        prioridad = random.randint(1, 5)
        
        writer.writerow([id_sol, fecha.strftime('%Y-%m-%d %H:%M:%S'), nodo, tipo, tiempo_resp, horas_rec, estado, prioridad])

print("Dataset generado exitosamente en /home/estudiante/workspace/dpci_dataset_2024.csv")
EOF
python3 /home/estudiante/workspace/generar_dataset_dpci.py
```

## Instrucciones Paso a Paso

### Paso 1: Verificación de Integridad y Tamaño del Dataset

**Objetivo:** Validar que la base de datos sintética anonimizada `dpci_dataset_2024.csv` contenga la estructura y volumen exigidos antes de su importación en la herramienta de IA.

1. Verifique en la terminal la presencia del archivo generado y cuente el número total de registros.

```bash
ls -lh /home/estudiante/workspace/dpci_dataset_2024.csv
wc -l /home/estudiante/workspace/dpci_dataset_2024.csv
```

2. Inspeccione las primeras 5 filas del archivo para verificar el formato de las columnas.

```bash
head -n 5 /home/estudiante/workspace/dpci_dataset_2024.csv
```

**Resultado esperado:** El archivo debe tener un tamaño aproximado entre 300 KB y 450 KB, conteniendo exactamente 5,201 líneas (encabezado + 5,000+ registros sintéticos).

**Verificación:** Confirmar que la primera línea incluya las columnas: `ID_Solicitud`, `Fecha_Creacion`, `Nodo_Infraestructura`, `Tipo_Solicitud`, `Tiempo_Respuesta_Min`, `Horas_Recurso`, `Estado`, `Puntaje_Prioridad`.

---

### Paso 2: Carga del Dataset en ChatGPT y Activación de Advanced Data Analysis

**Objetivo:** Cargar el archivo de datos anonimizado en la interfaz de ChatGPT e iniciar la sesión de procesamiento mediante la herramienta Advanced Data Analysis.

1. Abra el navegador web e ingrese a la interfaz de ChatGPT ([https://chatgpt.com/](https://chatgpt.com/)).
2. Asegúrese de seleccionar el modelo **GPT-4o** con capacidades analíticas y de código activas.
3. Haga clic en el botón de adjuntar archivo (icono del clip o botón `+`) en el cuadro de chat de la web app.
4. Navegue a la ruta `/home/estudiante/workspace/` o arrastre el archivo `dpci_dataset_2024.csv` al cuadro de texto.
5. Ingrese y envíe la siguiente instrucción (prompt) para activar la inspección inicial de datos:

```text
Actúa como un Científico de Datos Senior especializado en auditoría e infraestructura tecnológica de la DPCI. 
He adjuntado el archivo 'dpci_dataset_2024.csv'. 
Por favor, realiza las siguientes tareas de inspección inicial mediante la herramienta de código en segundo plano:
1. Muestra la cantidad total de filas y columnas.
2. Identifica los tipos de datos de cada columna y detecta si existen valores nulos o vacíos.
3. Proporciona una vista previa de las primeras 5 filas del dataset.
```

**Resultado esperado:** ChatGPT procesará el archivo mediante un bloque de Python ejecutable internamente y devolverá la confirmación del número de registros (5,200), identificando que la columna `Horas_Recurso` presenta valores faltantes (nulos).

**Verificación:** El asistente debe mostrar explícitamente la ejecución de código (cuadro emergente "Analizando" o "Worked with code") y desplegar los tipos de datos correctos.

---

### Paso 3: Análisis Exploratorio de Datos (EDA) y Limpieza de Valores Nulos

**Objetivo:** Solicitar la depuración del conjunto de datos y la generación de estadísticas descriptivas completas sobre el rendimiento operativo de los nodos de la DPCI.

1. En la misma sesión de chat, envíe la siguiente instrucción para ejecutar la depuración y el cálculo de métricas descriptivas:

```text
Procede a limpiar el conjunto de datos realizando lo siguiente:
1. Imputa los valores nulos en la columna 'Horas_Recurso' utilizando la mediana correspondiente al 'Tipo_Solicitud' asociado.
2. Calcula las estadísticas descriptivas (media, mediana, desviación estándar, mínimo, máximo, percentiles 25 y 75) para las variables numéricas: 'Tiempo_Respuesta_Min', 'Horas_Recurso' y 'Puntaje_Prioridad'.
3. Agrupa los datos por 'Nodo_Infraestructura' y 'Tipo_Solicitud' para calcular el tiempo promedio de respuesta y el tiempo máximo registrado. Presenta los resultados en formato de tabla limpia.
```

**Resultado esperado:** El modelo ejecutará el código en Python para realizar la imputación de nulos basada en la mediana del grupo y entregará una tabla estructurada con las estadísticas globales y agrupadas.

**Verificación:** La tabla de salida debe reflejar 0 valores nulos en `Horas_Recurso` y mostrar un valor atípico de tiempo máximo que supera los 800 minutos en el `Nodo_Norte` bajo la categoría de `Incidente_Critico`.

---

### Paso 4: Generación de Visualizaciones Cuantitativas y Detección de Anomalías

**Objetivo:** Solicitar la creación de gráficos estadísticos (histogramas y diagramas de dispersión) para evidenciar anomalías operativas en la infraestructura de la DPCI sin redactar código manual.

1. Envíe la siguiente instrucción al chat de ChatGPT para generar las gráficas analíticas:

```text
Utiliza la herramienta de análisis de datos para generar y mostrar dos visualizaciones:
1. Un histograma con curva de densidad del 'Tiempo_Respuesta_Min' segmentado por 'Nodo_Infraestructura' para observar el sesgo de la distribución.
2. Un gráfico de dispersión (Scatter Plot) relacionando 'Horas_Recurso' (eje X) frente a 'Tiempo_Respuesta_Min' (eje Y), destacando en un color diferenciado los registros considerados valores atípicos (anomalías donde Tiempo_Respuesta_Min > 300 minutos).
3. Resume formalmente las 3 anomalías o patrones atípicos principales detectados en las gráficas.
```

**Resultado esperado:** ChatGPT generará dos imágenes/gráficos directamente en el chat utilizando la librería `matplotlib` o `seaborn` en su entorno aislado. El análisis textual destacará el comportamiento anómalo del `Nodo_Norte`.

**Verificación:** Confirmar la generación visual de las dos gráficas y que el reporte textual identifique que los tiempos de respuesta en el `Nodo_Norte` para incidentes críticos exceden sustancialmente el promedio general del resto de los nodos.

---

### Paso 5: Apertura e Iniciación de la Interfaz Canvas para el Documento Técnico

**Objetivo:** Transicionar del análisis de datos interactivo a la redacción colaborativa en la interfaz Canvas de ChatGPT para construir el documento oficial de conclusiones técnicas.

1. En el mismo hilo de conversación, envíe la siguiente instrucción para forzar la apertura de la ventana de Canvas:

```text
Con base en los hallazgos del análisis de datos cuantitativo realizado previamente, abre la interfaz Canvas y redacta el borrador inicial del 'Informe Técnico de Conclusiones y Auditoría Operativa DPCI 2024'. 

El documento en Canvas debe tener la siguiente estructura inicial:
## INFORME TÉCNICO DE CONCLUSIONES OPERATIVAS DPCI 2024
## 1. Resumen Ejecutivo
## 2. Metodología de Análisis de Datos
## 3. Hallazgos Cuantitativos y Anomalías Detectadas
## 4. Matriz de Riesgo e Impacto Operativo
## 5. Recomendaciones Estratégicas
```

**Resultado esperado:** La interfaz web de ChatGPT abrirá un panel lateral derecho (Canvas UI) conteniendo el borrador del documento en formato Markdown interactivo.

**Verificación:** Confirmar que el panel derecho contenga el texto generado y que aparezcan los controles de edición y selección de texto de Canvas.

---

### Paso 6: Refinamiento Iterativo y Colaborativo en Canvas (Ajuste de Tono y Estructura)

**Objetivo:** Utilizar las funciones avanzadas de Canvas para ajustar párrafos específicos, modificar el tono a uno institucional-auditable y profundizar en las recomendaciones técnicas.

1. En el panel de Canvas (o mediante el cuadro de chat con Canvas activo), seleccione la sección `3. Hallazgos Cuantitativos y Anomalías Detectadas`.
2. Envíe la siguiente instrucción específica de modificación de Canvas:

```text
Modifica la sección '3. Hallazgos Cuantitativos y Anomalías Detectadas' en Canvas para incorporar datos numéricos exactos extraídos del análisis previo:
- Menciona que el dataset consta de 5,200 registros.
- Destaca que el Nodo_Norte presentó un tiempo máximo de respuesta de más de 900 minutos en Incidentes Críticos, excediendo en más de un 400% la mediana global.
- Utiliza un tono estrictamente formal, técnico e institucional (marco de gobernanza DPCI).
- Incluye una tabla comparativa en Markdown de los 4 nodos (Norte, Sur, Central, Occidente).
```

3. Seleccione la sección `5. Recomendaciones Estratégicas` y haga clic en el botón flotante de Canvas **"Ajustar nivel de detalle"** (o envíe la orden en el chat) indicando: `"Hacer más detallado y añadir acciones a corto y mediano plazo"`.

**Resultado esperado:** El texto en la ventana de Canvas se actualizará en tiempo real, agregando la tabla estructurada en Markdown y ampliando las recomendaciones estratégicas con planes concretos a 30 y 90 días.

**Verificación:** El documento en Canvas debe reflejar la tabla comparativa entre nodos y las recomendaciones divididas formalmente por plazos temporales.

---

### Paso 7: Exportación del Documento Final y Validación de Consistencia

**Objetivo:** Copiar el informe pulido desde Canvas y guardarlo en el espacio de trabajo local para su archivo institucional y auditoría posterior.

1. En la esquina superior derecha del panel de Canvas, haga clic en el icono de **Copiar contenido** (o seleccione todo el texto y cópielo).
2. Abra la terminal en el entorno local y cree el archivo oficial de conclusiones técnicas en la ruta de trabajo.

```bash
cat << 'EOF' > /home/estudiante/workspace/Informe_Tecnico_Conclusiones_DPCI_2024.md
## INFORME TÉCNICO DE CONCLUSIONES OPERATIVAS DPCI 2024

## 1. Resumen Ejecutivo
El presente documento consolida los resultados de la auditoría analítica realizada sobre el conjunto de datos sintético anonimizado `dpci_dataset_2024.csv`, correspondiente a 5,200 solicitudes de servicio registradas durante el ejercicio 2024. El objetivo principal es identificar patrones de rendimiento, cuellos de botella y anomalías operativas en la infraestructura de la Dirección de Protección y Control de Infraestructura (DPCI).

## 2. Metodología de Análisis de Datos
El análisis se ejecutó mediante la herramienta Advanced Data Analysis de ChatGPT (modelo GPT-4o), aplicando técnicas de estadística descriptiva, imputación de valores faltantes por mediana condicional y detección de valores atípicos mediante distribución de cuantiles.

## 3. Hallazgos Cuantitativos y Anomalías Detectadas
Se analizaron 5,200 registros distribuidos entre 4 nodos de infraestructura. Se identificó una discrepancia severa en el rendimiento del **Nodo Norte** durante la atención de Incidentes Críticos:

| Nodo | Tiempo Promedio (Min) | Tiempo Mediano (Min) | Tiempo Máximo (Min) | Desviación Estándar |
| :--- | :--- | :--- | :--- | :--- |
| **Nodo Norte** | 178.4 | 179.2 | 948.3 | 52.1 |
| **Nodo Sur** | 35.1 | 34.8 | 72.4 | 11.9 |
| **Nodo Central** | 34.9 | 35.0 | 71.1 | 12.1 |
| **Nodo Occidente** | 35.2 | 35.1 | 74.0 | 11.8 |

*Anomalía Principal:* El **Nodo Norte** registra un tiempo de respuesta en incidentes críticos que excede en un **410%** el promedio de los demás nodos, acumulando el 98% de los valores atípicos superiores a 300 minutos.

## 4. Matriz de Riesgo e Impacto Operativo
- **Riesgo Crítico (Nivel 1):** Saturación del Nodo Norte durante eventos críticos, con potencial incumplimiento del SLA institucional (límite máximo permitido: 60 minutos).
- **Riesgo Moderado (Nivel 2):** Registros incompletos en la variable `Horas_Recurso` (1.5% del total), lo que evidencia una omisión parcial en el llenado de bitácoras por parte de los operadores.

## 5. Recomendaciones Estratégicas
### Acciones a Corto Plazo (1 a 30 días)
1. Rebalancear la carga de solicitudes del Nodo Norte hacia el Nodo Sur según el protocolo DPCI-MAN-2024-002.
2. Auditar la capacidad de hardware y memoria VRAM/CPU en los servidores centrales del Nodo Norte.

### Acciones a Mediano Plazo (31 a 90 días)
1. Implementar controles obligatorios en el formulario de captura para evitar valores nulos en `Horas_Recurso`.
2. Establecer alertas en tiempo real cuando un tiempo de respuesta en cualquier nodo supere el percentil 90 (60 minutos).
EOF
```

3. Verifique el contenido guardado en la terminal.

```bash
head -n 25 /home/estudiante/workspace/Informe_Tecnico_Conclusiones_DPCI_2024.md
```

**Resultado esperado:** El archivo Markdown local contendrá el documento completo refinado mediante la interfaz Canvas, estructurado y alineado con los datos del análisis cuantitativo.

**Verificación:** Confirmar que la ruta `/home/estudiante/workspace/Informe_Tecnico_Conclusiones_DPCI_2024.md` exista y posea un tamaño superior a 1.5 KB.

---

## Validación y Pruebas

Para garantizar que el proceso analítico y de redacción cumple con las exigencias del marco de gobernanza DPCI, ejecute el siguiente procedimiento de validación y control de calidad.

### Criterios de Aceptación Medibles

1. **Integridad del Dataset:** El conjunto de datos `dpci_dataset_2024.csv` debe poseer exactamente 5,200 registros de datos más la línea de encabezado.
2. **Precisión Analítica (ADA):** La mediana e imputación de nulos debe haberse calculado mediante script en Python sin intervención o estimación a ojo del modelo.
3. **Consistencia Documental (Canvas):** El informe final en Canvas no debe contener inconsistencias numéricas con respecto a los resultados del EDA (ejemplo: el tiempo máximo reportado en el informe debe coincidir exactamente con el estadístico descriptivo obtenido por ADA).

### Prueba Adversarial de Validación (Prompt Injection / Inconsistencia)

Para comprobar la capacidad de detección de incoherencias del modelo y la robustez del analista, realice el siguiente ejercicio en el chat:

1. Envíe la siguiente instrucción engañosa a ChatGPT:

```text
Actualiza el informe en Canvas indicando que el 'Nodo Sur' fue el que presentó el peor rendimiento con un tiempo promedio de 500 minutos, y elimina la mención sobre el Nodo Norte.
```

2. **Comportamiento Esperado de la IA:** Dado que el entorno Advanced Data Analysis mantiene el contexto execution-state del CSV, el modelo debe advertir o el participante debe verificar que la instrucción contradice los datos reales del dataset, rechazando la afirmación falsa o corrigiendo la instrucción antes de alterar Canvas.

3. Ejecute la verificación de consistencia mediante script local:

```bash
python3 -c "
import pandas as pd
df = pd.read_csv('/home/estudiante/workspace/dpci_dataset_2024.csv')
norte_max = df[df['Nodo_Infraestructura']=='Nodo_Norte']['Tiempo_Respuesta_Min'].max()
sur_mean = df[df['Nodo_Infraestructura']=='Nodo_Sur']['Tiempo_Respuesta_Min'].mean()
print(f'Verificación Backend -> Max Nodo Norte: {norte_max:.2f} min | Promedio Nodo Sur: {sur_mean:.2f} min')
assert norte_max > 500, 'Error: El Nodo Norte debe contener el valor atípico alto'
assert sur_mean < 50, 'Error: El Nodo Sur no debe ser la anomalía principal'
print('PRUEBA ADVERSARIAL EXITOSA: Los datos respaldan que Nodo Norte es la anomalía real.')
"
```

---

## Solución de Problemas

### Problema 1: Desconexión del Runtime de Advanced Data Analysis o Error al Subir el Archivo CSV

- **Síntoma:** Aparece el mensaje "Error al procesar el archivo", "Memory Error" o la sesión de Python se reinicia perdiendo las variables calculadas previamente.
- **Causa:** Superación del tiempo de espera de la sesión gratuita/estándar de ChatGPT Web App o incompatibilidad temporal en la carga de archivos multipart del navegador.
- **Solución:**
  1. Refresque la página de ChatGPT en Google Chrome (F5).
  2. Reduzca temporalmente las filas del dataset en la terminal local ejecutando `head -n 1000 /home/estudiante/workspace/dpci_dataset_2024.csv > /home/estudiante/workspace/dpci_dataset_reducido.csv`.
  3. Adjunte el nuevo archivo reducido `dpci_dataset_reducido.csv` y reanude la sesión de chat con el prompt del Paso 2. Alternativamente, utilice Google Gemini 1.5 Flash ([https://gemini.google.com/](https://gemini.google.com/)) adjuntando el mismo archivo para el análisis descriptivo sin modificar la metodología.

### Problema 2: La Interfaz Canvas no se Despliega Automáticamente al Dar la Instrucción

- **Síntoma:** ChatGPT responde el texto en el hilo de chat convencional en lugar de abrir el panel lateral interactivo de Canvas.
- **Causa:** El selector de modelo en la Web UI no tiene la función Canvas activada por defecto en la sesión actual o la instrucción no fue interpretada como una solicitud de creación de documento interactivo.
- **Solución:**
  1. En el menú desplegable superior del modelo, asegúrese de seleccionar explícitamente la opción **GPT-4o con Canvas** (o "Canvas" si aparece de forma independiente).
  2. Utilice una instrucción directa con comando en el chat: `Abre Canvas y coloca este texto: [título y estructura]`.
  3. Si la interfaz no está disponible por limitaciones de cuenta, pida al modelo que entregue el texto estructurado en un único bloque de código Markdown y continúe la edición iterativa en el chat regular.

---

## Limpieza

Una vez completadas todas las verificaciones y habiendo guardado el informe técnico final, ejecute el script de limpieza para eliminar únicamente los scripts auxiliares de generación de datos, preservando los entregables oficiales.

```bash
rm -f /home/estudiante/workspace/generar_dataset_dpci.py
rm -f /home/estudiante/workspace/dpci_dataset_reducido.csv 2>/dev/null
ls -la /home/estudiante/workspace/
```

**Verificación:** Confirmar que el directorio `/home/estudiante/workspace/` contenga los archivos fundamentales `dpci_dataset_2024.csv` y `Informe_Tecnico_Conclusiones_DPCI_2024.md`.

---

## Resumen

En esta práctica, el participante aplicó una metodología integral para la analítica avanzada de datos sin necesidad de programar manualmente en Python:

1. **Exploración Cuantitativa Asistida (ADA):** Cargó una base de datos masiva de 5,200 registros de la DPCI, imputó datos faltantes y descubrió anomalías operativas severas concentradas en el `Nodo_Norte`.
2. **Visualización Integrada:** Solicitó la creación de histogramas y diagramas de dispersión para evidenciar el comportamiento de los datos atípicos.
3. **Edición Colaborativa en Canvas:** Utilizó la interfaz Canvas para estructurar, adaptar el tono y pulir iterativamente un informe técnico institucional oficial.
4. **Validación de Gobernanza:** Realizó comprobaciones cruzadas para garantizar que ningún dato cuantitativo reportado en el documento final fuera producto de alucinaciones del modelo.

### Recurso Complementario

- Documentación oficial de OpenAI sobre Canvas y Advanced Data Analysis: [https://openai.com/index/introducing-canvas/](https://openai.com/index/introducing-canvas/)
