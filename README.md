# Rhyzome — Informe final de trabajo de grado

## 1. Información general

Este repositorio contiene el código fuente LaTeX del informe final del proyecto **Rhyzome – Generador Procedural de Mapas 2D para Videojuegos**, desarrollado en el marco de la Maestría Virtual en Ingeniería de Sistemas y Computación de la Universidad del Valle.

El repositorio tiene como propósito mantener el control de versiones, facilitar la elaboración del documento académico y garantizar la reproducibilidad de su compilación.

## 2. Descripción del proyecto

Rhyzome es un prototipo orientado a la generación procedural de mapas bidimensionales para videojuegos, mediante la integración de algoritmos de generación procedural y técnicas de Machine Learning.

El informe documenta el contexto, la justificación, el diseño, la arquitectura, la implementación, la experimentación, la gestión del proyecto, las pruebas y los resultados obtenidos durante su desarrollo.

## 3. Herramientas utilizadas

| Herramienta | Propósito |
|---|---|
| LaTeX | Elaboración del documento académico |
| TeXstudio | Editor principal del documento |
| MiKTeX | Distribución y compilación de LaTeX |
| PdfLaTeX | Motor de compilación |
| BibLaTeX | Gestión de referencias bibliográficas |
| Biber | Procesamiento de la bibliografía |
| Git | Control de versiones |
| GitHub | Respaldo remoto del código fuente |
| Visual Studio Code | Editor alternativo |
| PlantUML | Elaboración de diagramas técnicos |

## 4. Estructura del repositorio

```text
rhyzome-informe-final/
├── capitulos/
├── imagenes/
├── build/
├── main.tex
├── referencias.bib
├── .gitignore
└── README.md
```

| Elemento | Descripción |
|---|---|
| `capitulos/` | Archivos LaTeX correspondientes a los capítulos del informe. |
| `imagenes/` | Figuras, diagramas, capturas y evidencias gráficas. |
| `build/` | Directorio opcional para los archivos generados durante la compilación. |
| `main.tex` | Archivo principal y configuración general del documento. |
| `referencias.bib` | Base de datos de referencias bibliográficas. |
| `.gitignore` | Exclusión de archivos auxiliares y temporales. |
| `README.md` | Documentación del repositorio. |

## 5. Requisitos de instalación

Para editar y compilar el documento se requiere:

- MiKTeX actualizado.
- TeXstudio.
- Biber.
- Git.
- Los paquetes LaTeX requeridos por el documento.

MiKTeX puede instalar automáticamente los paquetes faltantes durante la compilación, según su configuración.

## 6. Configuración de TeXstudio

TeXstudio es el editor principal utilizado para la elaboración del informe final de Rhyzome. La configuración del entorno permite centralizar los archivos generados durante la compilación en el directorio `build/`, manteniendo organizada la estructura del repositorio.

### 6.1. Configuración general

Acceder a:

**Opciones → Configurar TeXstudio → Compilación**

Establecer las siguientes herramientas:

| Parámetro | Configuración |
|---|---|
| Compilador predeterminado | PdfLaTeX |
| Herramienta de bibliografía predeterminada | Biber |
| Visor PDF | Visor PDF externo |
| Distribución LaTeX | MiKTeX |

El documento utiliza BibLaTeX y Biber para la gestión de referencias bibliográficas con estilo APA.

### 6.2. Configuración del compilador PdfLaTeX

Acceder a:

**Opciones → Configurar TeXstudio → Comandos**

Localizar el campo correspondiente a PdfLaTeX y establecer el siguiente comando:

```bash
pdflatex.exe -synctex=1 -interaction=nonstopmode -output-directory=build %.tex
```

Descripción de los parámetros:

| Parámetro | Descripción |
|---|---|
| `-synctex=1` | Habilita la sincronización entre el código fuente y el PDF. |
| `-interaction=nonstopmode` | Permite continuar la compilación sin interrupciones interactivas. |
| `-output-directory=build` | Establece el directorio de salida de los archivos generados. |
| `%.tex` | Identifica el archivo LaTeX que se debe compilar. |

Antes de realizar la primera compilación, verificar que el directorio `build/` exista en la raíz del repositorio.

### 6.3. Configuración de Biber

En la sección de comandos de TeXstudio, verificar que Biber se encuentre disponible y configurado como herramienta predeterminada para el procesamiento de la bibliografía.

Si la configuración predeterminada funciona correctamente, no es necesario modificarla.

En caso de que Biber no encuentre el archivo `main.bcf` generado dentro del directorio `build/`, se puede utilizar la siguiente configuración alternativa:

```bash
biber.exe --input-directory=build --output-directory=build %
```

Esta configuración permite localizar los archivos de control bibliográfico y almacenar los resultados del procesamiento en el directorio de compilación.

### 6.4. Configuración de las opciones avanzadas

Acceder a:

**Opciones → Configurar TeXstudio**

Activar la opción **Mostrar opciones avanzadas**, ubicada en la parte inferior de la ventana de configuración.

Posteriormente, ingresar a:

**Compilación → Directorios de búsqueda adicionales**

En el campo correspondiente a **Archivo PDF**, establecer:

```text
build
```

Esta configuración permite que TeXstudio localice el documento PDF generado dentro del directorio `build/`, en lugar de buscarlo en la raíz del repositorio.

### 6.5. Configuración del visor PDF externo

Para visualizar el documento compilado mediante Microsoft Edge, acceder a:

**Opciones → Configurar TeXstudio → Comandos**

Localizar el campo **Visor PDF externo** y establecer el siguiente comando:

```bash
"C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" --single-argument ?am.pdf &
```

La ruta del ejecutable corresponde a una instalación habitual de Microsoft Edge en Windows. En caso de utilizar una ubicación diferente, deberá ajustarse según el entorno.

La combinación del visor externo y los directorios de búsqueda adicionales permite abrir el archivo PDF generado dentro de `build/`.

### 6.6. Configuración de la compilación automática

En la sección **Compilación**, se puede configurar la opción de compilación y visualización mediante la siguiente secuencia:

```text
txs:///pdflatex | txs:///biber | txs:///pdflatex | txs:///pdflatex | txs:///view
```

Esta secuencia permite ejecutar:

1. Compilación inicial del documento.
2. Procesamiento de las referencias bibliográficas.
3. Actualización de las citas y referencias cruzadas.
4. Consolidación de los índices y la numeración.
5. Visualización del documento PDF.

La compilación completa resulta especialmente útil cuando se incorporan nuevas referencias bibliográficas, figuras, tablas o capítulos.

## 7. Compilación del documento

### 7.1. Compilación desde TeXstudio

Para compilar el informe:

1. Abrir TeXstudio.
2. Abrir el archivo `main.tex`.
3. Verificar que el directorio `build/` exista.
4. Ejecutar la opción **Compilar y visualizar** mediante la tecla `F5`.
5. Verificar que el documento PDF se genere correctamente.

El documento compilado estará disponible en:

```text
build/main.pdf
```

Cuando se requiera actualizar la bibliografía o las referencias cruzadas, ejecutar la secuencia completa de compilación.

### 7.2. Compilación desde la terminal

Como alternativa a TeXstudio, el documento puede compilarse desde una terminal ubicada en la raíz del repositorio.

Crear el directorio `build/` si todavía no existe:

```bash
mkdir build
```

Ejecutar los siguientes comandos:

```bash
pdflatex -synctex=1 -interaction=nonstopmode -output-directory=build main.tex
biber --input-directory=build --output-directory=build main
pdflatex -synctex=1 -interaction=nonstopmode -output-directory=build main.tex
pdflatex -synctex=1 -interaction=nonstopmode -output-directory=build main.tex
```

Como resultado, se generará el archivo `build/main.pdf`.

### 7.3. Verificación de la compilación

Después de compilar el documento, verificar:

- Generación correcta del archivo PDF.
- Visualización de todos los capítulos.
- Actualización de la tabla de contenido.
- Actualización del índice de figuras y tablas.
- Resolución de las referencias cruzadas.
- Generación de la bibliografía en estilo APA.
- Ausencia de errores críticos de compilación.

## 8. Gestión de archivos auxiliares

Durante la compilación, LaTeX genera archivos auxiliares necesarios para gestionar referencias cruzadas, bibliografía, índices y registros de ejecución.

Estos archivos se centralizan en el directorio `build/`.

```text
build/
├── main.aux
├── main.bbl
├── main.bcf
├── main.blg
├── main.lof
├── main.log
├── main.lot
├── main.out
├── main.run.xml
├── main.synctex.gz
├── main.toc
└── main.pdf
```

Los archivos generados durante la compilación no forman parte del código fuente del informe y deben excluirse del control de versiones mediante `.gitignore`.

### 8.1. Exclusión del directorio de compilación

El archivo `.gitignore` debe incluir la siguiente regla:

```gitignore
build/
```

Debido a que Git no realiza el seguimiento de directorios vacíos, después de clonar el repositorio será necesario crear el directorio `build/` antes de ejecutar la primera compilación.

### 8.2. Limpieza de archivos auxiliares

En caso de inconsistencias relacionadas con referencias bibliográficas, índices o numeración, se recomienda:

1. Cerrar el documento PDF.
2. Eliminar los archivos generados dentro de `build/`.
3. Conservar el directorio `build/`.
4. Ejecutar nuevamente la secuencia completa de compilación.
5. Verificar el resultado obtenido.

### 8.3. Solución de problemas frecuentes

| Problema | Solución |
|---|---|
| El PDF se busca en la raíz del repositorio. | Verificar que `build` esté configurado en los directorios de búsqueda adicionales para archivos PDF. |
| El PDF no se genera. | Verificar la existencia del directorio `build/` y revisar el registro de compilación. |
| Las referencias aparecen como `??`. | Ejecutar nuevamente PdfLaTeX hasta resolver las referencias cruzadas. |
| Las citas bibliográficas no aparecen correctamente. | Ejecutar Biber y posteriormente PdfLaTeX dos veces. |
| Biber no encuentra `main.bcf`. | Verificar los directorios de entrada y salida de Biber. |
| Faltan paquetes LaTeX. | Verificar la configuración de instalación automática de paquetes en MiKTeX. |
| El visor externo no abre el documento. | Verificar la ruta del ejecutable de Microsoft Edge y la configuración de búsqueda del PDF. |
| El PDF muestra una versión anterior. | Verificar que se esté visualizando `build/main.pdf` y no un archivo generado anteriormente en la raíz. |


## 7. Compilación del documento

Abrir el archivo `main.tex` desde TeXstudio.

Para garantizar la correcta generación de referencias, bibliografía, índices y numeración, ejecutar la siguiente secuencia:

1. PdfLaTeX.
2. Biber.
3. PdfLaTeX.
4. PdfLaTeX.

También es posible realizar la compilación desde una terminal ubicada en la raíz del repositorio:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

Como resultado se generará el archivo `main.pdf`.

## 8. Archivos auxiliares

Durante la compilación, LaTeX genera archivos auxiliares necesarios para gestionar referencias cruzadas, bibliografía, índices y registros de ejecución.

Estos archivos no forman parte del código fuente del informe y se encuentran excluidos del control de versiones mediante `.gitignore`.

Opcionalmente, se puede configurar un directorio `build/` para centralizar los archivos generados. Esta configuración requiere ajustar el compilador, Biber y el visor PDF.

En caso de inconsistencias de compilación, se pueden eliminar los archivos auxiliares desde las herramientas de limpieza de TeXstudio y ejecutar nuevamente el proceso completo.

## 9. Gestión de versiones

El repositorio utiliza Git para registrar los cambios realizados durante la elaboración del informe.

Se recomienda realizar commits por cada modificación significativa, capítulo terminado o revisión documental.

Ejemplos:

```bash
git add .
git commit -m "docs: actualizar contexto y justificacion"
git push
```

Convenciones recomendadas:

| Prefijo | Propósito |
|---|---|
| `docs:` | Redacción o actualización de contenido |
| `fix:` | Corrección de errores |
| `refactor:` | Reorganización de la estructura documental |
| `chore:` | Actualización de configuraciones |
| `style:` | Ajustes de formato y presentación |

## 10. Lineamientos de mantenimiento

- Mantener los capítulos organizados en archivos independientes.
- Almacenar las imágenes y diagramas en el directorio correspondiente.
- Registrar las referencias bibliográficas en `referencias.bib`.
- Verificar la compilación antes de realizar un commit.
- Evitar incorporar archivos auxiliares al repositorio.
- Mantener la documentación alineada con la versión definitiva del prototipo Rhyzome.
- Verificar las referencias cruzadas, citas, figuras y tablas antes de generar la versión final.

## 11. Estado del documento

**Estado:** En elaboración.

**Proyecto:** Rhyzome.

**Programa académico:** Maestría Virtual en Ingeniería de Sistemas y Computación.

**Institución:** Universidad del Valle.

**Año:** 2026.

## 12. Propósito académico

Este repositorio está destinado a la elaboración, mantenimiento y consolidación del informe final de trabajo de grado del proyecto Rhyzome.