# Setup Guide General

## Inteligencia Artificial Generativa Essentials y Ciencia de datos aplicada

| Control documental | Información |
|---|---|
| Clave del curso | Custom IA_GEN_ESSE_DS AB (Priv) |
| Versión del documento | 1.0 |
| Estado | BORRADOR: revisión documental completa; pendiente de validación con cuentas de participante |
| Instructor responsable | Por asignar por Netec |
| Fecha de elaboración | 2026-11-09 |
| Fecha de última validación | 2026-11-09 (revisión del repositorio) |
| Repositorio de laboratorios | [github.com/Netec-Mx/Custom-IA-GEN-ESSE-DS-AB-Priv](https://github.com/Netec-Mx/Custom-IA-GEN-ESSE-DS-AB-Priv) |
| Rama y revisión analizada | `changes_course`, versión 1.0 |
| Alcance revisado | 3 capítulos, 10 módulos, 10 prácticas, 30 archivos de recursos, README principal y Setup Guide |
| Modalidad del entorno | Web (servicios SaaS gratuitos) con aplicaciones de ofimática locales o en la web |

[Inicio](README.md)

# Objetivo

Preparar, para cada participante, un equipo con navegador actualizado, una suite de ofimática (Microsoft 365 o LibreOffice) y cuentas gratuitas activas en ChatGPT, Microsoft Copilot, Google (Gemini y NotebookLM) y Claude, además de los archivos ficticios de las 10 prácticas descargados en una carpeta local. El entorno se considera listo cuando las validaciones obligatorias de la sección [Validación del Entorno](#validacion-entorno) se aprueban con la cuenta de un participante. No se requiere instalar lenguajes de programación ni usar la terminal.

# Requisitos de Hardware

| Recurso | Mínimo requerido | Recomendado | Observaciones |
|---|---|---|---|
| Procesador y arquitectura | 64 bits, 2 núcleos | 4 núcleos o más | Las herramientas de IA se ejecutan en la nube |
| Memoria RAM | 8 GB | 16 GB | Varias pestañas de navegador y Excel abiertos a la vez |
| Espacio libre | 2 GB | 5 GB | Los archivos de las prácticas ocupan menos de 5 MB |
| Pantalla | 1366 x 768 | 1920 x 1080 o dos monitores | Facilita comparar respuestas entre herramientas (Práctica 6) |
| Conectividad | 10 Mbps por participante | 25 Mbps por participante | Necesaria durante todo el curso |

# Sistemas Operativos Compatibles

| Sistema operativo | Edición y versión | Arquitectura | Condición de soporte o validación |
|---|---|---|---|
| Windows 11 | Home, Pro o Enterprise | x64 | Plataforma base del curso; compatible según fabricante; pendiente de validar |
| macOS | 14 o posterior | Apple silicon o Intel | Compatible según fabricante; no validado. Los atajos de teclado cambian (Cmd en lugar de Ctrl) |

Las instrucciones de las prácticas usan Windows 11 y los nombres de menú de Microsoft Excel y Word en español.

# Software Requerido

| Componente | Edición y versión requerida | Arquitectura | Obligatorio u opcional | Fuente oficial |
|---|---|---|---|---|
| Navegador Microsoft Edge o Google Chrome | Versión estable vigente | x64 | Obligatorio | [google.com/chrome](https://www.google.com/chrome/) |
| Microsoft Excel, Word y PowerPoint | Microsoft 365 (escritorio o web) | x64 | Obligatorio (o LibreOffice como alternativa) | [microsoft365.com](https://www.microsoft365.com/) |
| LibreOffice | Versión estable vigente | x64 | Opcional, si no hay Microsoft 365 | [libreoffice.org](https://www.libreoffice.org/download/download-libreoffice/) |
| ChatGPT | Servicio administrado, plan gratuito | N/A | Obligatorio (Práctica 9) | [chatgpt.com](https://chatgpt.com/) |
| Microsoft Copilot Chat | Servicio administrado, versión gratuita | N/A | Obligatorio (Práctica 7) | [copilot.microsoft.com](https://copilot.microsoft.com/) |
| Google Gemini | Servicio administrado, plan gratuito | N/A | Opcional (prácticas 1 a 6, a elección del instructor) | [gemini.google.com](https://gemini.google.com/) |
| Google NotebookLM | Servicio administrado, plan gratuito | N/A | Obligatorio (Práctica 8) | [notebooklm.google.com](https://notebooklm.google.com/) |
| Claude | Servicio administrado, plan gratuito | N/A | Obligatorio (Práctica 10) | [claude.ai](https://claude.ai/) |

Los servicios de IA son administrados y cambian sus modelos y límites sin previo aviso. Registre la fecha de prueba y las limitaciones observadas en el [Registro de validación](#registro-validacion).

# Herramientas y Dependencias

## Paquetes, frameworks y componentes adicionales

| Dependencia | Versión o restricción | Componente que la necesita | Método de instalación o habilitación |
|---|---|---|---|
| Carga de archivos en ChatGPT | Disponible en el plan gratuito con límites diarios | Prácticas 1 a 6 y 9 | Incluida; requiere sesión iniciada |
| Análisis de datos (Advanced Data Analysis) | Disponible en el plan gratuito con límites | Práctica 9 | Incluido; se activa al adjuntar un CSV ([documentación](https://help.openai.com/en/articles/8437071-data-analysis-with-chatgpt)) |
| Canvas de ChatGPT | Disponible en el plan gratuito | Práctica 9 | Herramienta del cuadro de mensaje |
| Proyectos de Claude | Según el plan y la versión disponible | Práctica 10 | Panel izquierdo de Claude ([documentación](https://support.claude.com/en/articles/9517075-what-are-projects)); si no está disponible, se adjuntan los archivos en el chat |
| Fuentes de NotebookLM | Límite de fuentes por cuaderno del plan gratuito | Práctica 8 | Panel **Fuentes** ([documentación](https://support.google.com/gemininotebook/answer/16215270)) |
| Archivos de las prácticas | Versión 1.0 del repositorio | Prácticas 1 a 10 | Carpetas `CapituloNN/PracticaNN/recursos/` |

## Licencias, cuentas y permisos

| Recurso o servicio | Licencia o suscripción | Cuenta o rol requerido | Permiso mínimo | Responsable de habilitación |
|---|---|---|---|---|
| ChatGPT | Gratuita | Cuenta de OpenAI | Usuario | Cada participante |
| Microsoft Copilot | Gratuita | Cuenta Microsoft (personal, de trabajo o escuela) | Usuario | Cada participante o TI de la DPCI |
| Gemini y NotebookLM | Gratuita | Cuenta de Google | Usuario | Cada participante |
| Claude | Gratuita | Cuenta de Anthropic | Usuario | Cada participante |
| Microsoft 365 | Licencia institucional o cuenta gratuita de Office en la web | Cuenta Microsoft | Usuario | TI de la DPCI |
| Acceso al repositorio | Repositorio privado de GitHub | Cuenta de GitHub con acceso de lectura, o paquete ZIP entregado por el instructor | Lectura | Netec |

Las cuentas son personales. No registrar contraseñas ni códigos de verificación en este repositorio. Si la DPCI restringe alguno de estos servicios en su red, debe autorizarlo antes del curso o el instructor debe elegir una alternativa para los módulos 3 a 6.

# Instalación y Configuración

## 1. Obtener los materiales

- Repositorio autorizado: [github.com/Netec-Mx/Custom-IA-GEN-ESSE-DS-AB-Priv](https://github.com/Netec-Mx/Custom-IA-GEN-ESSE-DS-AB-Priv) (botón **Code > Download ZIP**) o paquete ZIP entregado por el instructor.
- Revisión: rama `main` una vez integrados los cambios de `changes_course`.
- Directorio de trabajo: `Documentos\Practicas_IA_DPCI\` con una subcarpeta por práctica (`Practica01` a `Practica10`).
- Archivos de entrada: carpetas `recursos` de cada práctica.

## 2. Instalar o habilitar los componentes

### Navegador y ofimática

1. Verificar que Edge o Chrome estén actualizados (**Configuración > Acerca de**).
2. Verificar acceso a Excel, Word y PowerPoint (escritorio o [microsoft365.com](https://www.microsoft365.com/)), o instalar LibreOffice.

**Resultado esperado:** El navegador indica que está actualizado y Excel abre un libro en blanco.

### Cuentas de IA

1. Crear o iniciar sesión en cada servicio de la tabla **Software Requerido**.
2. Aceptar los términos de uso de cada servicio.
3. Enviar un mensaje de prueba en cada uno (por ejemplo, *"Responde solo OK"*).

**Resultado esperado:** Cada servicio responde con la sesión iniciada.

### Carpetas de trabajo

1. Descomprimir el ZIP del repositorio.
2. Crear `Documentos\Practicas_IA_DPCI\` y, dentro, las carpetas `Practica01` a `Practica10`.
3. Copiar a cada carpeta el contenido de `CapituloNN\PracticaNN\recursos` correspondiente.

**Resultado esperado:** 10 carpetas con 30 archivos en total.

## 3. Preparar archivos de configuración

No se requieren archivos de configuración. Todos los archivos de entrada están en las carpetas `recursos` y no deben modificarse antes de la práctica.

# Variables de Entorno

No se requieren variables de entorno: el curso no usa programación ni línea de comandos.

# Configuración Base para los Laboratorios

## Parámetros comunes

| Parámetro | Valor o convención | Observaciones |
|---|---|---|
| Raíz de trabajo | `Documentos\Practicas_IA_DPCI\` | Una carpeta por práctica |
| Nombre de entregables | `Nombre_[INICIALES].ext` | Ejemplo: `Matriz_Verificacion_Cruzada_LMR.xlsx` |
| Datos | Ficticios o anonimizados | Nunca cargar información real de la DPCI en las prácticas |
| Separador de fórmulas | `;` (o `,` según configuración regional) | Prácticas 2 y 5 |

## Estructura de carpetas

```text
Documentos\Practicas_IA_DPCI\
├── Practica01\ ... Practica10\   Archivos de cada práctica y entregables
```

## Recursos compartidos

No hay recursos compartidos entre participantes. Cada participante trabaja con sus propias cuentas y archivos.

## Correcciones de coherencia

| Inconsistencia o dependencia omitida | Configuración unificada | Ajuste necesario en las copias de trabajo |
|---|---|---|
| El repositorio tenía 8 carpetas numeradas por módulo; el temario define 3 capítulos | `Capitulo01` a `Capitulo03`, con una carpeta y un README por práctica | Ninguno |
| Las prácticas requerían terminal Linux, bash y Python, contrario al perfil "sin experiencia en programación" | Pasos con Word, Excel, Bloc de notas y herramientas web | Ninguno |
| Los archivos de entrada se generaban con scripts | 30 archivos listos para descargar en `recursos` | Ninguno |
| Los enlaces apuntaban a otro repositorio (`261108-Custom-IA-GEN-ESSE-DS-AB-Priv`) | Enlaces relativos dentro del repositorio | Ninguno |
| Los KPIs esperados de la práctica de clasificación no coincidían con su propia tabla | Valores de referencia recalculados y rangos esperados | Ninguno |
| La práctica comparativa rellenaba la matriz con resultados predefinidos | El participante registra su propia evidencia | Ninguno |
| Se citaban versiones de modelos de 2024 | Se indica "versión gratuita vigente" | Registrar la versión observada en cada curso |
| El archivo se llamaba `SETUP_GUIDE.md` | `Setup_Guide.md`, según la plantilla | Ninguno |

# Servicios Externos Requeridos

| Servicio | URL, endpoint o región | Uso | Acceso requerido |
|---|---|---|---|
| ChatGPT | [chatgpt.com](https://chatgpt.com/) | Prácticas 1 a 6 (opcional) y 9 | Cuenta gratuita |
| Microsoft Copilot | [copilot.microsoft.com](https://copilot.microsoft.com/) | Prácticas 1 a 6 (opcional) y 7 | Cuenta Microsoft |
| Google Gemini | [gemini.google.com](https://gemini.google.com/) | Prácticas 1 a 6 (opcional) | Cuenta de Google |
| Google NotebookLM | [notebooklm.google.com](https://notebooklm.google.com/) | Práctica 8 | Cuenta de Google |
| Claude | [claude.ai](https://claude.ai/) | Prácticas 1 a 6 (opcional) y 10 | Cuenta gratuita |
| GitHub | [github.com](https://github.com/) | Descarga de materiales | Lectura del repositorio |

## Configuración de red

| Origen | Destino | Protocolo y puerto | Sentido | Condición |
|---|---|---|---|---|
| Equipo del participante | chatgpt.com, copilot.microsoft.com, gemini.google.com, notebooklm.google.com, claude.ai, github.com | HTTPS 443 | Saliente | Los dominios no deben estar bloqueados por el proxy o firewall institucional |

# Creación de Entornos / Máquinas Virtuales / Emuladores

No aplica. El curso no requiere máquinas virtuales, contenedores ni emuladores.

<a id="validacion-entorno"></a>

# Validación del Entorno

| ID | Componente o capacidad | Procedimiento | Resultado esperado | Evidencia mínima |
|---|---|---|---|---|
| V-01 | Navegador | Abrir [github.com](https://github.com/) y el repositorio | El repositorio se muestra | Captura |
| V-02 | Archivos | Abrir `Lote_Expedientes_Sensibles_DPCI.xlsx` en Excel | El archivo muestra 20 registros | Captura |
| V-03 | ChatGPT | Adjuntar `DPCI_Solicitudes_2024_reducido.csv` y pedir el número de filas | 1,000 filas | Captura |
| V-04 | Copilot | Adjuntar `DPCI_Metricas_Operativas_2024.xlsx` y pedir el número de registros | 48 registros | Captura |
| V-05 | NotebookLM | Crear un cuaderno y subir un PDF de la Práctica 8 | La fuente aparece en el panel | Captura |
| V-06 | Claude | Adjuntar `Doc1_Reporte_Incidente_TI.pdf` y pedir un resumen | Resumen del documento | Captura |
| V-07 | Gemini (opcional) | Adjuntar `Diagrama_Arquitectura_DPCI.png` y pedir describirlo | Describe los nodos y su carga | Captura |

**Criterio de entorno listo:** V-01 a V-06 aprobadas. V-07 es opcional porque las prácticas 1 a 6 permiten usar otra herramienta.

# Comandos de Verificación

No aplica. El curso se valida únicamente en interfaces web con los procedimientos V-01 a V-07, sin instalar herramientas de línea de comandos.

# Troubleshooting

| Síntoma | Causa probable | Comprobación | Corrección | Validación posterior |
|---|---|---|---|---|
| Un servicio de IA no carga | Bloqueo de red institucional | Abrir el sitio desde otra red | Solicitar a TI la autorización del dominio | V-03 a V-07 |
| Límite de mensajes o archivos alcanzado | Restricciones de la versión gratuita | Mensaje del servicio | Esperar, usar otra herramienta (prácticas 1 a 6) o los archivos reducidos | Repetir el paso |
| Un archivo no se adjunta | Formato o tamaño no admitido | Mensaje de error | Pegar el contenido como texto o usar la versión reducida | Repetir el paso |
| Las fórmulas de Excel marcan error | Separador regional o Excel en inglés | Ver el mensaje de error | Cambiar `;` por `,` o usar los nombres de función en inglés | V-02 |
| NotebookLM no está disponible | Restricción de edad o de región de la cuenta | Mensaje de acceso | Usar una cuenta de Google que cumpla los requisitos | V-05 |

# Checklist Final

- [ ] Navegador actualizado y suite de ofimática disponible.
- [ ] Cuentas gratuitas activas en ChatGPT, Copilot, Google (Gemini y NotebookLM) y Claude.
- [ ] Dominios de las herramientas permitidos en la red institucional.
- [ ] 30 archivos de las prácticas descargados en `Documentos\Practicas_IA_DPCI\`.
- [ ] Validaciones V-01 a V-06 aprobadas y registradas.

# Resumen

Para iniciar el curso, cada participante necesita un navegador actualizado, Excel, Word y PowerPoint (o LibreOffice), cuentas gratuitas en las cuatro plataformas de IA y los archivos ficticios de las prácticas descargados. No se requiere programación ni instalación de lenguajes o herramientas de línea de comandos.

<a id="registro-validacion"></a>

## Registro de validación

| Fecha | Responsable | Plataforma o entorno probado | Resultado | Limitaciones o acciones pendientes |
|---|---|---|---|---|
| 2026-11-09 | Desarrollo de contenido Netec | Revisión del repositorio: estructura, enlaces, recursos, tiempos y alineación con el temario | APTO para publicación del repositorio | No se ejecutaron las prácticas con cuentas de participante. Pendiente: V-01 a V-07 |

## Referencias oficiales

| Documento o recurso | URL | Fecha de consulta |
|---|---|---|
| Análisis de datos con ChatGPT | https://help.openai.com/en/articles/8437071-data-analysis-with-chatgpt | 2026-11-09 |
| Política de privacidad de OpenAI | https://openai.com/es-ES/policies/privacy-policy/ | 2026-11-09 |
| Declaración de privacidad de Microsoft | https://www.microsoft.com/es-es/privacy/privacystatement | 2026-11-09 |
| Ayuda de NotebookLM: agregar fuentes | https://support.google.com/gemininotebook/answer/16215270 | 2026-11-09 |
| Política de privacidad de Google | https://policies.google.com/privacy | 2026-11-09 |
| Proyectos de Claude | https://support.claude.com/en/articles/9517075-what-are-projects | 2026-11-09 |
| Política de privacidad de Anthropic | https://www.anthropic.com/legal/privacy | 2026-11-09 |

[Inicio](README.md)
