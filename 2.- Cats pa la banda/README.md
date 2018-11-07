# Guia de Cats Pa la Banda
Vamos a crear una pagina desde cero utilizando HTML y CSS. La pagina que vamos a crear se va a ver algo asi:

[Demo](https://youthful-jones-d39abb.netlify.com/)

## Setup
1. Abre tu editor de texto (Visual Studio Code, Atom, etc)
2. Crea una nueva carpeta con el nombre que quieras.
3. Crea un nuevo archivo llamado `index.html`.
4. Crea otro archivo llamado `index.css`. Aqui iran los estilos para nuestra pagina.
5. En donde se encuentran tus archivos `html` y `css`, crea una nueva carpeta llamada `imagenes`. Aqui es donde estaremos guardando nuestras imagenes.

Como hemos visto, todas las paginas HTML tienen una estructura inicial muy parecidas. Empezaremos con una estructura inicial default.

```html
<!DOCTYPE html>
<html lang="es">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">

  <title>Mi titulo</title>
</head>

<body>
  <h1>Hola Mundo!</h1>
</body>
</html>
```

Puedes copiar y pegar este codigo a tu `index.html`.
**Nota**: Si usas Visual Studio Code, dentro de tu `index.html` puedes escribir 'html:5' seguido con la tecla Tab y te genera este ultimo codigo automaticamente.

6. Abre tu archivo `index.html` en Chrome (navegador). Podras ver los cambios que que vayas haciendo (recuerda siempre guardar tu arvhico con cada cambio).


## El HTML
Recuerden que el HTML solo define la estructura del contenido de nuestra pagina. Si volvemos a abrir el [Demo](https://youthful-jones-d39abb.netlify.com/), vemos las diferentes secciones de textos e imagenes que tiene.

Vamos a empezar definiendo el contenido de nuestra pagina.

1. Primero, crea una etqueta `<header>` que es donde vendra el encabezado de nuestra pagina (La barra azul de arriba del [Demo](https://youthful-jones-d39abb.netlify.com/)) con una imagen, titulo principal (`h1`) y uno secundario (`h5`).

```html
<header>
  <img src="logo.png" alt="Logo Cats" height="35">
  <h1>Pa la Banda</h1>
  <h5>Todos los felinos que quieras</h5>
</header>
```

2. Luego agregamos el contenido principal de nuestra pagina que ira dentro de una etiqueta `<main>`

```html
<main>
  <h2>Estamos aqui para atisfacer tu necesidad por gatos.</h2>

  <p>No nos crees? Velo aqui mismo con tus propios ojos!</p>

  <a href="">Ve a los Gatos!</a>

  <p>Antes</p>
  <img src="https://i.imgur.com/5bcut7t.jpg" alt="Mad cat">

  <p>Despues</p>
  <img src="https://i.redd.it/5egrdrdt0ld01.jpg" alt="Happy cat">

  <p>Contactate con nosotros para saber en quien confiar!</p>
  <button>Saludanos</button>

  <blockquote>Las personas a las que no les gustan los gatos, seguramente en otra vida fueron ratones.</blockquote>
</main>
```

Si lo intentamos ver en el navegador, notaran que solo es texto en negro con unas imagenes.


## El CSS
Hay varias maneras de aplicar estilos a nuestro HTML. Lo que CSS usa para aplicar estilos son selectores.

Por ejemplo, si tenemos un titulo `<h1>Gato Alpha</h1>`, utilizando CSS podemos aplicarle un estilo:

Selector Generico:

`<h1>Gato Alpha</h1>`

```css
h1 {
  color: blue;
}
```

Selector de Clase:

`<h1 class="titulo">Gato Alpha</h1>`

```css
.titulo { /* punto antes de nombre de clase obligatorio */
  color: green;
}
```

**Nota**: A TODAS las etiquetas de HTML le puedes agregar un atributo `class` para darle estilo con CSS.

Vamos a darle estilo a algunos elementos HTML que tenemos definidos.

1. Entra a `index.css` y escribe lo siguiente:

```css
body {
  font-family:'Trebuchet MS'; /* Definir font para nuestra pagina completa */
  margin: 0;
  padding: 0;
}

header {
  background: #00AEB4;
  color: #393E45;
  padding: 20px;
  text-align: center;
}

main {
  margin: 0 auto; /* Centrar todo nuestro main */
  text-align: center; /* Centrar todo el texto en nuestro main */
}
```

2. No olvidemos "importar" nuestro archivo CSS al de HTML. Dentro de la etiqueta `<head>` de HTML creamos un `link`.

```html
<link rel="stylesheet" href="index.css">
```

Abran en el navegador y notaran unos cambios, sobretodo en el `header` de la pagina.

En el header del [Demo](https://youthful-jones-d39abb.netlify.com/) los titulos e imagen se despliegan de forma horizontal pero en nuestro archivo se despliegan verticalmente.

## CSS Display
Hay una propiedad en CSS que se llama `display` que se encarga de como se despliegan los elementos de HTML. Esta propiedad tiene varios valores posibles, los que nos importan ahorita son `inline`, `inline-block`, y `block`. Cual es la diferencia entre esos valores? Checa [este link](https://www.w3schools.com/css/tryit.asp?filename=trycss_inline-block_span1).

Unas etiquetas por default son `inline` (`<a>`, `<img>`, `<span>`, etc) y otras son `block` por default (`<h1>`, `<p>`, `<div>`, etc)

## Contenedores
El uso de `<div>` (contenedores) es necesario para poder desplegar adecuadamente la pagina. Vamos a modificar lo que hicimos del HTML para que cada elemento tenga su contendor. De una vez les agregamos atributos `class` para poder ponerle estilos chilos.

1. Vamos a modificar lo que va dentro de las etiquetas de `<main>` y `<header>`. Y agregar classes!

```html
<header>
  <img src="logo.png" alt="Logo Cats" height="35">
  <h1 class="titulo">Pa la Banda</h1>
  <h5 class="subtitulo">Todos los felinos que quieras</h5>
</header>

<main>
  <div class="intro">
    <h2>Estamos aqui para atisfacer tu necesidad por gatos.</h2>

    <p>No nos crees? Velo aqui mismo con tus propios ojos!</p>

    <a class="link" href="#gatitos">Ve a los Gatos!</a>
  </div>

  <div id="gatitos"></div>
  <div class="gato-antes">
    <div class="gato-antes-contenedor">
      <p>Antes</p>
      <img class="foto-antes" src="https://i.imgur.com/5bcut7t.jpg" alt="Mad cat">
    </div>
  </div>

  <div class="gato-despues">
    <div class="gato-despues-contenedor">
      <p>Despues</p>
      <img class="foto-despues" src="https://i.redd.it/5egrdrdt0ld01.jpg" alt="Happy cat">
    </div>
  </div>

  <div class="contacto">
    <p>Contactate con nosotros para saber en quien confiar!</p>
    <button>Saludanos</button>
  </div>

  <div class="cita">
    <blockquote>Las personas a las que no les gustan los gatos, seguramente en otra vida fueron ratones.</blockquote>
  </div>
</main>
```

Si abren esto en el navegador, no cambiara nada! Ahora con CSS podemos ponerle estilo a nuestras etiquetas por medio de clases.

Vamos a agregar mas estilos a nuestro `index.css`.

2. Empezamos con los titulos en el header:

```css
.titulo, .subtitulo {
  display: inline; /* Esto hara que se desplieguen horizontalmente (en la misma linea) */
  margin: 0;
}
```

3. Le ponemos estilo a `intro` para que tenga el fondo gris y el espaciado. Tambien le damos color al `link`.

```css
.intro {
  background: lightgrey;
  padding: 100px; /* espaciado */
}

.link {
  color: #00AEB4;
  font-size: 30px; /* tamaño de fuente */
  display: block; /* Esto hara que el link aparezca en su propia linea (salto) */
}
```

4. Ahora utilizando varias veces la propiedad de `display` de CSS, acomodamos la seccion del historial de foto de gatos (antes y despues).

```css
.gato-antes {
  display: inline; /* Que los contenedores principales aparezcan lado a lado (en misma linea) */
  font-weight: bold; /* letra en bold */
}
.gato-antes-contenedor {
  display: inline-block; /* Necesitamos esto para que el 'Antes' y 'Despues' se desplieguen arriba de las imagenes. */
}

.gato-despues {
  display: inline; /* Que los contenedores principales aparezcan lado a lado (en misma linea) */
  font-weight: bold;
}
.gato-despues-contenedor {
  display: inline-block;
}

.foto-antes {
  width: 300px;
}

.foto-despues {
  width: 300px;
}
```

5. Aplicarle estilo a las secciones faltantes de 'contacto' y 'cita':

```css
.cita {
  background: url('https://png.pngtree.com/thumb_back/fw800/back_pic/03/63/42/2657ac290bb918c.jpeg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center center;
  width: 100%;
  height: 500px;
}

.cita blockquote {
  padding-top: 250px;
  font-size: 20px;
}

button {
  background: #00AEB4;
  color: white;
  padding: 20px;
  font-size: 15px;
  border-radius: 10px;
  transition: ease-in-out 0.3s;
}

button:hover {
  padding-left: 50px;
  padding-right: 50px;
  font-size: 15px;
}
```


## Nyon Cat Sorpresa
Agreguen este css al final de su archivo:

```css
body {
  overflow-x: hidden;
}

.nyan-cat {
  position: absolute;
  top: 115px;
  left: -10%;
  width: 90px;
  height: 60px;
  background-image: url('https://media.tenor.co/images/b0dacd0bb277315b8582d2d0e07d62a8/tenor.gif');
  background-size: contain;
  background-repeat: no-repeat;
  animation-name: leftToRight;
  animation-duration: 8s;
  animation-delay: 1s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  z-index: 10;
}

@keyframes leftToRight {
  0% { left: -90px;}
  100%{ left : 100%;}
}
```

Como pueden ver, define una clase llamada `nyon-cat`. Creen un `<div></div>` asi vacio con la clse `nyon-cat` y coloquenlo en alguna parte del HTML (dentro del `body` claro).
