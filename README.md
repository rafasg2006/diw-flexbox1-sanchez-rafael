# Solicitud Erasmus+ · Partes A, B y C

**Autor:** Rafael Sánchez  
**Repositorio:** https://github.com/rafasg2006/diw-flexbox1-sanchez-rafael

Maquetación de la cabecera, pie y formulario de una web de solicitud de beca Erasmus+ para una movilidad a Polonia, aplicando Flexbox, CSS Grid y efectos avanzados (variables, sombras, degradados y transiciones).

## Estructura

```text
index.html
README.md
styles/
└── estilos.css
```

Para visualizarla, abrir `index.html` en un navegador. No necesita instalación, dependencias ni compilación.

## Proceso de maquetación

1. Se partió de `indexParteA.html`, guardándolo como `index.html`. Se conservaron su estructura semántica, textos, clases y atributos de accesibilidad. El enlace a `styles/estilos.css` ya estaba incluido.
2. Se estableció una base común con `box-sizing: border-box`, márgenes a cero en el cuerpo y tipografía del sistema. Los colores se expresaron en hexadecimal: azul `#1b3959`, fondo `#f4f6f9`, blanco `#ffffff` y amarillo `#ffd166`.
3. El cuerpo se convirtió en un contenedor Flexbox vertical con `min-height: 100vh`. El contenido principal crece con `flex: 1`, de forma que el pie permanece abajo cuando hay poco contenido y se desplaza con el documento si este crece.
4. La cabecera y el pie usan `display: flex`, `justify-content: space-between`, `align-items: center` y `flex-wrap: wrap`. Así se separan la marca y el menú, y el texto legal y sus enlaces, permitiendo varias filas cuando falta espacio.
5. Las listas de enlaces también usan Flexbox con `flex-wrap: wrap` y `gap`. Se eliminaron las viñetas y los márgenes y rellenos iniciales de las listas.
6. Se seleccionó la opción actual mediante `.menu__enlace[aria-current="page"]`: lleva negrita y borde inferior amarillo. Un borde transparente en el resto de enlaces evita saltos de altura.
7. Los enlaces superiores se subrayan con `:hover` y `:focus-visible`. El foco de teclado también dispone de un contorno amarillo visible.
8. Se utilizaron `rem`, `em` y porcentajes para espacios y tamaños, sin alturas fijas en la cabecera y el pie. `overflow-wrap: anywhere` permite dividir textos largos en espacios muy reducidos.

## Comprobaciones

- **W3C CSS Validator (01/11/2026 y 13/11/2026):** validación del contenido de `styles/estilos.css` con perfil CSS3: **0 errores**.
- **Adaptación:** comprobados anchos efectivos de 2330, 1280, 768, 400 y 320 píxeles CSS. En 320 píxeles, el documento mide también 320 píxeles de ancho: no hay desbordamiento horizontal. La cabecera aumenta su altura al repartir el menú en varias filas y el pie sigue al contenido.
- **Selección:** el navegador confirma peso de fuente `700` para el enlace con `aria-current="page"`.
- Para repetir la comprobación de zoom, ampliar con `Ctrl` + `+` y comprobar que los enlaces pasan de línea y todo el contenido sigue accesible mediante desplazamiento vertical.

## Alcance

La Parte A prepara la cabecera y el pie con Flexbox. La Parte B incorpora la estructura, la ayuda y el formulario con Grid. La Parte C aplica los efectos visuales avanzados (variables, sombras, degradados y transiciones) exclusivamente desde `styles/estilos.css`, sin alterar el marcado HTML original ni requerir imágenes. El HTML suministrado conserva sus botones de borrador y envío como maqueta: no incluye almacenamiento ni un servicio de recepción de solicitudes. Los destinos `href="#"` pertenecen al HTML original y son marcadores de posición.

## Git y entrega

La carpeta de trabajo ya tenía un repositorio Git inicializado, vacío y sin remoto. Se creó el repositorio público en GitHub, se vinculó como `origin` y se preparó un commit descriptivo con los tres archivos solicitados.

Para obtener una copia después de la publicación:

```sh
git clone https://github.com/rafasg2006/diw-flexbox1-sanchez-rafael.git
cd diw-flexbox1-sanchez-rafael
```

## Parte B: formulario con Grid

Se utiliza el nuevo `indexParteB.html` como `index.html`, conservando sus clases, etiquetas, controles y orden semántico. El original se mantiene como referencia. La cabecera, el menú y el pie conservan las reglas Flexbox de la Parte A.

- Diseño móvil primero: formulario y ayuda en una columna, en el orden del HTML, y botones apilados.
- Exactamente dos consultas de medios con `min-width`: `40em` para los campos y la botonera, y `56em` para la estructura de formulario y ayuda en paralelo.
- Cada bloque usa una rejilla de seis columnas desde `40em`. Los catorce campos se asignan mediante `grid-area` y plantillas de áreas con nombre, también en móvil.
- Tarjetas blancas con borde y leyenda sobre el borde. Separación de `1.5rem` entre bloques; campos con `1rem` entre filas y `1.5rem` entre columnas en escritorio.
- Opciones automáticas con `repeat(auto-fit, minmax(min(100%, 8rem), 1fr))`, sin consultas adicionales. El mínimo nunca supera el ancho disponible.
- Teléfono en dos columnas; el prefijo utiliza un intervalo adaptable de hasta `9.5rem` y el número una columna `minmax(0, 1fr)`.
- Controles y botones de al menos `2.75rem` (44 píxeles con tamaño base de 16 píxeles). Anchuras mínimas a cero para evitar que fechas o archivos fuercen las columnas.
- Ayuda de carta y límite en dos columnas desde `40em`; botonera con una columna vacía que separa Borrar de Guardar y Enviar.
- Ayuda lateral y pasos con Grid. Foco visible, enlace de salto y borde rojo solo para campos inválidos después de interacción (`:user-invalid`).
- Cabecera de CSS con paleta e índice, y secciones delimitadas por comentarios. Sin tablas de maquetación ni flotados.

## Parte C: variables, sombras, degradados y transiciones

Se añaden los acabados y efectos visuales avanzados del apunte de CSS sin tocar el HTML ni añadir imágenes:

1. **Paleta en variables CSS (`:root`):**
   - Todos los colores se declaran una única vez en la raíz (`:root`), utilizando nombres que describen su papel funcional y no su aspecto cromático (`--color-primario`, `--color-primario-claro`, `--color-primario-oscuro`, `--color-secundario-hover`, `--color-fondo`, `--color-superficie`, `--color-texto`, `--color-texto-inverso`, `--color-texto-secundario`, `--color-borde-control`, `--color-borde-tarjeta`, `--color-error`, `--color-enlace`, `--color-foco`, `--color-acento`, `--color-sombra-bloque` y `--color-sombra-texto`).
   - Se eliminaron todos los colores escritos de forma directa: no aparece ningún valor `#` ni función `rgba()` fuera del selector `:root`. Al modificar una variable en la raíz, el cambio se refleja en todo el documento.

2. **Relieve en las tarjetas:**
   - Los cuatro bloques del formulario (`.grupo`) y el cuadro de ayuda (`.ayuda`) proyectan una elevación sutil: `box-shadow: 0 0.125rem 0.5rem var(--color-sombra-bloque)` (desplazamiento vertical de 0,125 rem, desenfoque de 0,5 rem, sin desviación horizontal, con el azul oscuro corporativo `#12355b` al 20 % de opacidad).
   - La sombra se visualiza completa, sin cortes ni desbordamientos, en anchos de 1280, 768 y 320 píxeles.

3. **Sombra en la marca:**
   - El texto «DAW Mobility» de la cabecera incorpora relieve mediante `text-shadow: 0 0.0625rem 0.125rem var(--color-sombra-texto)` (0,0625 rem hacia abajo, 0,125 rem de desenfoque y negro al 45 % de opacidad), conservando total nitidez y legibilidad.

4. **Botón principal con relieve y respuesta interactiva:**
   - El botón principal «Enviar solicitud» (`.boton--principal`) cuenta con sombra en reposo (`0 0.125rem 0.25rem var(--color-sombra-bloque)`), en el mismo tono que las tarjetas. Mientras se mantiene presionado (`:active`), la sombra se reduce a una presencia mínima (`0 0.0625rem 0.0625rem var(--color-sombra-bloque)`) y el botón vuelve a su posición original (`transform: translateY(0)`).
   - Los otros dos botones no llevan sombra.
   - Al pasar el ratón (`:hover`) o enfocar con el teclado (`:focus-visible`), todos los botones suben 2 píxeles (`transform: translateY(-2px)`) y alternan su color de fondo: el botón principal oscurece su fondo a `#0b2340` (`--color-primario-oscuro`) y los otros dos botones adoptan un azul muy claro `#e3ebf6` (`--color-secundario-hover`).
   - La transición dura 0,2 s y se declaran explícitamente las propiedades afectadas (`background-color 0.2s, transform 0.2s, box-shadow 0.2s` para el principal y `background-color 0.2s, transform 0.2s` para los secundarios), sin recurrir a `all`.
   - La sombra no sustituye al contorno de foco (`outline`), que continúa visible tanto en ratón como en navegación por teclado.

5. **Degradado horizontal en cabecera y pie y medición de contraste:**
   - La cabecera y el pie se rellenan mediante un degradado lineal horizontal de izquierda a derecha (`linear-gradient(to right, var(--color-primario), var(--color-primario-claro))`), que transita desde el azul oscuro `#12355b` hasta el azul más claro `#1f6088`.
   - Se mantiene como respaldo un color liso debajo (`background-color: var(--color-primario)`).
   - **Medición del contraste (WCAG AA):**
     - **Valor obtenido:** relación de contraste de **6.80:1** para el texto blanco (`#ffffff`) sobre el extremo más claro del degradado (`#1f6088`), y de **12.46:1** sobre el extremo oscuro (`#12355b`).
     - **Criterio de conformidad:** supera ampliamente el umbral mínimo exigido de 4.5:1 para texto normal y 3.0:1 para texto grande según el criterio de conformidad 1.4.3 de las WCAG 2.1 (nivel AA), alcanzando incluso el nivel AAA en gran parte del componente.
     - **Procedimiento de medición:** se comprobó mediante las herramientas de desarrollo de Google Chrome (Chrome DevTools). Al inspeccionar los enlaces de la navegación en `.cabecera` y `.pie` situados en el extremo derecho del degradado, se abrió el panel *Elements* > *Styles* y se pulsó en la muestra del color del texto (`#ffffff`). El selector de color integrado (*Color Picker*) calcula automáticamente el ratio de contraste contra el fondo efectivo, indicando una puntuación de **6.80** con doble marca verde de verificación para nivel AA.

6. **Efecto de escala en los pasos de la ayuda:**
   - Al sobrevolar cualquiera de los tres pasos del cuadro de ayuda (`.ayuda__paso:hover`), el círculo numerado correspondiente (`.ayuda__numero`) aumenta suavemente un 10 % de tamaño mediante `transform: scale(1.1)` con una transición de 0,2 s (`transition: transform 0.2s`).
   - El uso de transformaciones CSS evita alterar el modelo de caja, de modo que el texto y los demás círculos no sufren desplazamientos ni solapamientos.
