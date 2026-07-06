# NOTICE — Componentes de terceros / Third-Party Components

**RedNote™** · Copyright © 2026 Bakoware. Todos los derechos reservados.

Este archivo lista los componentes de terceros incluidos o enlazados por RedNote,
junto con sus licencias. Son propiedad de sus respectivos autores y se usan bajo sus
propias licencias; nada en `LICENSE.md` las limita (ver su Sección 6).

> Actualizado: 2026-07-06. Revisar antes de cada distribución. Las licencias
> MIT/BSD/Apache/PSF exigen conservar sus avisos de copyright en las distribuciones
> binarias; las licencias **LGPL** y **AGPL** imponen requisitos adicionales (ver la
> nota al final).

## Dependencias

| Componente | Versión | Licencia | Uso |
|---|---|---|---|
| **PySide6** | ≥6.5 | **LGPL v3** (o licencia comercial de The Qt Company) | Enlaces oficiales de Qt: interfaz gráfica (ventanas, widgets, `QGraphicsView` del editor PDF) |
| **PyMuPDF** (`fitz`) | ≥1.23 | **AGPL v3** *o* licencia comercial de Artifex | Renderizado y manipulación de PDF |
| **Qt** (subyacente, vía PySide6) | 6.x | LGPL v3 | Toolkit nativo sobre el que corre PySide6 |
| **Python** | 3.14 | PSF License (permisiva) | Intérprete/runtime |

### Herramientas de compilación (no se distribuyen dentro de la app)

| Herramienta | Licencia | Nota |
|---|---|---|
| PyInstaller | GPL v2 **con excepción** para el ejecutable generado | Empaqueta el binario; la excepción permite distribuir el ejecutable resultante bajo tu propia licencia |
| Inno Setup | Licencia propia (gratuita, permite instaladores comerciales) | Genera el instalador de Windows |

---

## Nota sobre licencias LGPL y AGPL

**PySide6 / Qt (LGPL v3) — compatible con RedNote propietario.** La LGPL **sí** permite
distribuir software cerrado/propietario que enlace la biblioteca, siempre que se cumplan
sus condiciones: (1) **enlace dinámico** —el build de RedNote es *onedir*, con las
librerías de Qt como archivos separados, lo que satisface este punto—; (2) incluir el
**texto de la LGPL** y el aviso correspondiente junto al binario; y (3) permitir al
usuario **reemplazar** las librerías de PySide6/Qt por una versión compatible. Cumpliendo
esto, **no** se requiere licencia comercial de Qt para RedNote propietario.

**PyMuPDF / `fitz` (AGPL v3) — pendiente por resolver antes de vender.** La AGPL es
copyleft fuerte (más estricta que la GPL: añade la cláusula de uso en red). Mientras
RedNote se distribuya con la versión AGPL de PyMuPDF, la distribución del conjunto debe
respetar la AGPL, lo que **entra en tensión** con el carácter propietario descrito en
`LICENSE.md`. Para distribuir RedNote como software cerrado/propietario —especialmente si
en el futuro se **vende** o se cobra— será necesario, respecto de PyMuPDF, una de estas
opciones:

1. Adquirir la **licencia comercial de Artifex Software** para PyMuPDF/MuPDF, o
2. **Sustituir el motor de PDF** por uno con licencia permisiva (p. ej. `pypdfium2`,
   Apache-2.0/BSD), rehaciendo las partes de lectura/render/escritura que hoy usan
   `fitz`.

Esta cuestión es **independiente** de `LICENSE.md` y **debe resolverse antes de cualquier
venta o cobro** del proyecto. Conviene confirmarlo con un abogado y/o con el proveedor
comercial (Artifex).

**Copyright de Qt/PySide6:** © The Qt Company Ltd. y los contribuidores del Proyecto
Qt; usados por RedNote bajo LGPL v3. Los textos completos de la **LGPL-3.0** y la
**GPL-3.0** (referida por la LGPL), junto con el aviso de copyright de Qt/PySide6, **se
incluyen** en la carpeta `licenses/` que se instala con RedNote:
`licenses/LGPL-3.0.txt`, `licenses/GPL-3.0.txt` y `licenses/Qt-and-PySide6-NOTICE.txt`.

Los textos completos de las demás licencias de terceros se incluirán junto a los
binarios distribuidos según corresponda.

Contacto: **Bakoware** · aiscordesarrollo@gmail.com
