# Compilación y edición

Compilar siempre `informe.tex` desde `entrega1/`. La plantilla usa **XeLaTeX + Biber**, Times New Roman de 12 puntos, interlineado 1,5 y BibLaTeX APA.

## Requisitos

Distribución LaTeX con XeLaTeX, latexmk, Biber y los paquetes del preámbulo, incluido biblatex-apa. Times New Roman debe estar disponible para XeLaTeX. Si no está, instalar legalmente esa fuente o utilizar Calibri, también permitida por la pauta, cambiando `\setmainfont{Times New Roman}` por `\setmainfont{Calibri}`.

No sustituir por una fuente parecida sin comprobar cumplimiento. No se incluyen archivos de fuentes comerciales en el repositorio.

## Compilación local

```sh
latexmk -xelatex -interaction=nonstopmode -halt-on-error informe.tex
```

Alternativa sin latexmk, en este orden:

```sh
xelatex -interaction=nonstopmode -halt-on-error informe.tex
biber informe
xelatex -interaction=nonstopmode -halt-on-error informe.tex
xelatex -interaction=nonstopmode -halt-on-error informe.tex
```

Se genera `informe.pdf`. LaTeX no toma el nombre de salida de los datos de portada.

## Editor compartido

Cargar el contenido de `entrega1/`, seleccionar `informe.tex` como principal y XeLaTeX como compilador. Comprobar disponibilidad de Times New Roman o Calibri antes de redactar. Si el servicio requiere archivos de fuente, cargarlos solo cuando se cuente con autorización para usarlos.

Si GitHub es la fuente de trabajo, acordar quién sincroniza el editor compartido; evitar dos versiones divergentes.

## Archivo que se entrega

Renombrar una copia del PDF aprobado a **`InformeFinal GrupoXX.pdf`**, reemplazando XX por el número del grupo. El espacio después de InformeFinal es obligatorio según la pauta. Verificar que sea la última compilación, abrirlo y revisarlo antes de subir.

Los PDF generados se excluyen de Git; el PDF del caso y las figuras PDF sí se conservan.

## Convenciones de edición

- Las secciones contienen contenido, sin preámbulo ni `\begin{document}`.
- Citar con `\parencite{casoNubeSegura}` o `\textcite{clave}`; registrar fuentes verificadas en `referencias.bib`.
- Escapar caracteres de texto: `5\%`, `\_` y `\&`.
- Mantener identificadores únicos para figuras y tablas; incluir títulos, fuentes y referencias en el texto.
- El archivo principal fija 1.1, 1.2 y 1.3. En aportes usar `\subsubsection` y niveles inferiores, sin crear nuevas secciones principales.
- Resolver todos los `\pendiente{...}` antes de entregar; completar `datos.tex`, incluido profesor.
- Verificar citas resueltas, tablas legibles, márgenes y contenido del índice.

## Alcance de la verificación

La estructura puede revisarse sin un compilador; eso no confirma la generación del PDF. Cada integrante debe probar una compilación completa en el entorno acordado antes de comenzar.

