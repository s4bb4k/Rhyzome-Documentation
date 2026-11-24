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

Acceder a:

**Opciones → Configurar TeXstudio → Compilación**

Establecer las siguientes herramientas:

- Compilador predeterminado: PdfLaTeX.
- Herramienta de bibliografía predeterminada: Biber.
- Visor PDF: visor interno de TeXstudio.

El documento utiliza BibLaTeX y Biber para la gestión de referencias bibliográficas con estilo APA.

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