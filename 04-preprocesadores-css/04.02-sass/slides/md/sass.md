% Sass, un preprocesador CSS
% Adolfo Sanz De Diego
% Septiembre 2016



# El autor



## Adolfo Sanz De Diego

- Empecé **desarrollando aplicaciones web**, hasta que di el salto a la docencia.

- Actualmente soy **Asesor Técnico Docente** en el servicio TIC de la D.G de Infraestructuras y Servicios de la Consejería de Educación, Juventud y Deporte de la Comunidad de Madrid.

- Además colaboro como **formador especializado en tecnologías de desarrollo**.


## Algunos proyectos

- **Hackathon Lovers** <http://hackathonlovers.com>: un grupo creado para emprendedores y desarrolladores amantes de los hackathones.

- **Password Manager Generator** <http://pasmangen.github.io>: un gestor de contraseñas online.

- **MarkdownSlides** <https://github.com/asanzdiego/markdownslides>: un script para crear slides a partir de ficheros MD.


## ¿Donde encontrarme?

- Mi nick: **asanzdiego**

    - AboutMe:  <http://about.me/asanzdiego>
    - GitHub:   <http://github.com/asanzdiego>
    - Twitter:  <http://twitter.com/asanzdiego>
    - Blog:     <http://asanzdiego.blogspot.com.es>
    - LinkedIn: <http://www.linkedin.com/in/asanzdiego>
    - Google+:  <http://plus.google.com/+AdolfoSanzDeDiego>



# Introducción



## ¿Qué es?

- Less es un **pre-procesador de CSS**.

- Añade características como **variables, mixins, funciones, etc**.

## Ventajas

- El CSS es así **más fácil de mantener, personalizable y extensible**.

- Sass tiene una **sintaxis parecida a CSS**.

- Es el preprocesador que usa Bootstrap 4.0.



# Instalación



## Instalar Ruby

- Ubuntu:

~~~
sudo apt-get install ruby-full
~~~

- Windows: <http://rubyinstaller.org/>

- Mac: incluido

## Instalar Sass

- Después de instalar Ruby, ejecutar

~~~
gem install sass
~~~

## Preprocesar

- Un fichero

~~~
sass --watch input.scss:output.css
~~~

- Un directorio

~~~
sass --watch input/dir:output/dir
~~~



# Características



## Variables (I)

- El siguiente código:

~~~
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
~~~

## Variables (II)

- Se compila a:

~~~
body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}
~~~



## Scope

- Los **ámbitos de las variables** en Sass es muy similar a otros lenguajes:

~~~
$var: red;

#page {
  $var: white;
  #header {
    color: $var; // white
  }
}
~~~


## Reglas anidadas (I)

- El siguiente código:

~~~
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }
}
~~~

## Reglas anidadas (II)

- Se compila a:

~~~
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav li {
  display: inline-block;
}
~~~



## Parciales

- Es un archivo con un guión bajo:

~~~
_partial.scss
~~~

- Con esto Sass entiende que es un archivo parcial y que no debe generar CSS.



## Imports (I)

- Imaginemos el archivo **_reset.scss**:

~~~
html, body, ul {
  margin: 0;
  padding: 0;
}
~~~

## Imports (II)

- Y el archivo **base.scss**:

~~~
@import 'reset';

body {
  font: 100% Helvetica, sans-serif;
  background-color: #efefef;
}
~~~

## Imports (III)

- Se compila a:

~~~
html, body, ul, ol {
  margin: 0;
  padding: 0;
}

body {
  font: 100% Helvetica, sans-serif;
  background-color: #efefef;
}
~~~



## Mixins (I)

- El siguiente código:

~~~
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box {
  @include border-radius(10px);
}
~~~

## Mixins (I)

- Se compila a:

~~~
.box {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
~~~



## Extend (I)

- El siguiente código:

~~~
.message {
  color: #333;
}
.success {
  @extend .message;
  border-color: green;
}
.error {
  @extend .message;
  border-color: red;
}
~~~

## Extend (I)

- Se compila a:

~~~
.message, .success, .error, .warning {
  color: #333;
}
.success {
  border-color: green;
}
.error {
  border-color: red;
}
~~~



## Operadores (I)

- El siguiente código:

~~~
article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}

aside[role="complementary"] {
  float: right;
  width: 300px / 960px * 100%;
}
~~~

## Operadores (I)

- Se compila a:

~~~
article[role="main"] {
  float: left;
  width: 62.5%;
}

aside[role="complementary"] {
  float: right;
  width: 31.25%;
}
~~~



## Funciones (I)

- Sass dispone de una variedad de **funciones matemáticas, que manipulan cadenas, y que transforman los colores**:

~~~
@base: #f04615;
@list: 200, 500, 1200;

.class {
  width: extract(@list, 3);
  color: saturate(@base, 5%);
  background-color:
    lighten(@base, 25%);
}
~~~

## Funciones (II)

- El código anterior compila a:

~~~
.class {
  width: 1200;
  color: #f6430f;
  background-color: #f8a58d;
}
~~~



##  (I)

- El siguiente código:

~~~
~~~

## (I)

- Se compila a:

~~~
~~~



##  (I)

- El siguiente código:

~~~
~~~

## (I)

- Se compila a:

~~~
~~~



# Acerca de



## Licencia

- Estas **transparencias** están hechas con:
    - MarkdownSlides: <https://github.com/asanzdiego/markdownslides>

- Estas **transparencias** están bajo una licencia Creative Commons Reconocimiento-CompartirIgual 3.0:
    - <http://creativecommons.org/licenses/by-sa/3.0/es>

## Fuentes

- Transparencias:
    - <https://github.com/asanzdiego/curso-interfaces-web-2016/tree/master/04-preprocesadores-css/04.02-sass/slides>

- Código:
    - <https://github.com/asanzdiego/curso-interfaces-web-2016/tree/master/04-preprocesadores-css/04.02-sass/src>

## Bibliografía

- Documentación oficial de Sass
    - <http://sass-lang.com/>

- Para probar Sass
    - <http://www.sassmeister.com/>
