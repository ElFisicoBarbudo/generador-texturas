# Generador de texturas · El Físico Barbudo

Herramienta web para crear texturas a partir de simulaciones de sistemas complejos. Eliges una simulación, ajustas sus parámetros, le pones tu paleta de colores y exportas la imagen en PNG para usarla en redes sociales, fondos o material de marca.

**Úsala aquí:** https://elfisicobarbudo.github.io/generador-texturas/

No necesita instalación ni servidor. Es un único archivo (`index.html`) que calcula todo en el navegador. No se envía ningún dato a ningún sitio.

## Qué hace

1. **Simula** un sistema complejo en tiempo real (o lo calcula de una vez, según el tipo).
2. **Colorea** el resultado con una paleta de cinco colores que puedes editar, con niveles, inversión y fondo transparente.
3. **Da acabado** con grano y suavizado.
4. **Exporta** un PNG del tamaño que quieras, o graba un vídeo WebM de la animación.

Por defecto el lienzo es vertical **9:16** y la exportación sale a **1080 px de ancho** (1080×1920), el formato de story y reel.

## Simulaciones

**Dinámicas** (animadas, con pausa, paso a paso y velocidad):

| Simulación | Qué es |
| --- | --- |
| Modelo de Ising | Espines que se alinean con sus vecinos. Dominios en todas las escalas cerca de la temperatura crítica. |
| Segregación de Schelling | Agentes que se mudan si pocos vecinos son como ellos. |
| Reacción-difusión (Gray-Scott) | Manchas, corales, laberintos y gusanos. |
| Autómata cíclico | Espirales y ondas tipo piedra-papel-tijera. |
| Pila de arena abeliana | Criticalidad autoorganizada con patrones fractales. |
| Vida y variantes | Conway y otras reglas B/S, con rastro. |
| Moho mucilaginoso (Physarum) | Redes de venas formadas por agentes que siguen rastros. |
| Redes complejas | Barabási-Albert, mundo pequeño, Erdős-Rényi y geométricas. |
| Agregación por difusión (DLA) | Cristales dendríticos y corales. |
| Boids y bandadas | Bandadas con separación, alineación y cohesión. |
| Lenia | Vida continua con núcleo en anillo. Lenta en cuadrículas grandes. |
| Patrones de Turing multiescala | Rayas y manchas anidadas a varias escalas. |
| Modelo de Potts | Como Ising con q estados. |
| Incendio forestal | Modelo de Drossel-Schwabl. |
| Voronoi con relajación de Lloyd | Mosaicos que se ordenan hacia panales. |

**Estáticas** (se recalculan al cambiar un parámetro y a la resolución de exportación):

| Simulación | Qué es |
| --- | --- |
| Autómata elemental | Reglas de Wolfram 0 a 255. |
| Fractales | Mandelbrot, Julia, Barco ardiente y Tricornio, con zoom y desplazamiento. |
| Atractores extraños | Clifford, De Jong y Svensson. |
| Bifurcación logística | La ruta hacia el caos. |
| Lorenz, Rössler, Thomas, Aizawa | Flujos caóticos en 3D con ángulo de vista ajustable. |
| Péndulo doble: trayectorias | Cientos de péndulos que parten casi del mismo punto. |
| Percolación | Cúmulos fractales cerca del umbral crítico. |

Cada simulación trae **ajustes rápidos** con configuraciones interesantes.

## Cómo se usa

- **Cámara:** arrastra el lienzo para moverte y usa la rueda del ratón, el pellizco o los botones + y − para acercar. En las simulaciones periódicas, al alejar se ve el mosaico sin costuras. En los fractales el zoom recalcula la imagen.
- **Semilla:** el mismo número de semilla repite el mismo resultado. El botón "Nueva" elige otra.
- **Resolución de cuadrícula:** más alta da más detalle pero más lentitud. Para el móvil conviene 256 o menos.
- **Exportar:** el PNG respeta la posición y el zoom de la cámara.

## En el móvil

Abre la dirección en Safari (iPhone) o Chrome (Android) y añádela a la pantalla de inicio para usarla como una app. Al exportar, se abre una ventana con la imagen y el botón **Compartir o guardar**, que abre el menú del teléfono (Drive, Fotos, Instagram…). En pantallas estrechas el orden es: selector de simulación, lienzo fijo arriba, parámetros y después acabado y exportación.

## Detalles técnicos

- HTML, CSS y JavaScript sin dependencias, salvo las tipografías de Google Fonts.
- Las simulaciones se calculan en un índice de 0 a 255 por celda. La paleta convierte ese índice en color, así que se puede cambiar de color sin recalcular.
- Los generadores usan una semilla (mulberry32) para que los resultados se repitan.
