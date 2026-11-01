# Solicitud Erasmus+ · Parte A

**Autor:** Rafael Sánchez  
**Repositorio:** https://github.com/rafasg2006/diw-flexbox1-sanchez-rafael

Maquetación de la cabecera y el pie de una web de solicitud de beca Erasmus+ para una movilidad a Polonia, tomando como referencia las capturas del ejercicio.

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

- **W3C CSS Validator (01/11/2026):** validación real del contenido de `styles/estilos.css` en https://jigsaw.w3.org/css-validator/, perfil CSS3, respuesta SOAP: `validity=true`, **0 errores y 0 advertencias**.
- **Adaptación:** comprobados anchos efectivos de 2330, 400 y 320 píxeles CSS. En 320 píxeles, el documento mide también 320 píxeles de ancho: no hay desbordamiento horizontal. La cabecera aumenta su altura al repartir el menú en varias filas y el pie sigue al contenido.
- **Selección:** el navegador confirma peso de fuente `700` para el enlace con `aria-current="page"`.
- Para repetir la comprobación de zoom, ampliar con `Ctrl` + `+` y comprobar que los enlaces pasan de línea y todo el contenido sigue accesible mediante desplazamiento vertical.

## Alcance

Esta parte del ejercicio prepara únicamente la cabecera, el título y el pie. El formulario se desarrollará en otra parte. Los destinos `href="#"` pertenecen al HTML original y son marcadores de posición.

## Git y entrega

La carpeta de trabajo ya tenía un repositorio Git inicializado, vacío y sin remoto. Se creó el repositorio público en GitHub, se vinculó como `origin` y se preparó un commit descriptivo con los tres archivos solicitados.

Para obtener una copia después de la publicación:

```sh
git clone https://github.com/rafasg2006/diw-flexbox1-sanchez-rafael.git
cd diw-flexbox1-sanchez-rafael
```
