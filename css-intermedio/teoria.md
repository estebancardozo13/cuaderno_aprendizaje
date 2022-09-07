# CURSO DE CSS INTERMEDIO
 Bienvenida al curso, invitación al discord

 Contenido:

 2. Metodologia BEM
 3. Variables CSS
 4. Responsive y media queries
 5. Background
 6. Degradados
 7. PseudoClases
 8. PseudoElementos
 9. Un pequeño favor
 10. Formularios
 11. Listas en CSS
 12. Funciones en CSS
 13. Clip Path
 14. Filtros
 15. Diseño de columnas
 16. Flexbox
 17. Grid
 18. Transformaciones
 19. Transiciones
 20. Animaciones
 21. Clon de Youtube (PRONTO)

# 2-1 ¿Que es una metodologia en CSS?

## Ventajas
1. Permite la reutilización del codigo por lo que evita que lo repitamos

    - Las propiedades que comparten 2 elementos no se tienen que escribir 2 veces, se puede simplificar con la metodologia BEM.

2. Añade especifidad CONSISTENTE a todo el proyecto.
    - Es decir, ayuda a que el mantenimiento sea mejor, y la grafica sea mas plana en cuestion de especifidad.
      
3. Aumenta la independencia de nuestro codigo

    - Evita que escribamos mas CSS del que en realidad necesitamos.(Ayuda a prevenir el error de replicar la estructura del HTML en CSS)
---
  **EJEMPLO SIN METODOLOGIA BEM:** 
  - html
  ```html
  <!-- Tenemos 2 botones, 1 con fondo y otro transparente -->
  <a href="#" class="button">Botón</a>
  <a href="#" class="button-transparent">Botón transparente</a>
  ```
  - css
  ```css
  /* Como podemos ver SIN LA METODOLOGIA tenemos varias propiedades repetidas, que nos dificulta la realización del codigo */
  .button{
    /* Repetidas */
      display: inline-block;
      padding: 0.5em 1em;
      font-size: 1.2rem;
      text-decoration: none;
    /* Unicas */
      color: azure;
      background-color: royalblue;
      border-radius: 1.5em;
  }
  
  .button--transparent{
    /* Repetidas */
      display: inline-block;
      padding: 0.5em 1em;
      font-size: 1.2rem;
      text-decoration: none;
      /* Unicas */
      color: royalblue;
      background-color:transparent;
      border: 1px solid royalblue;
      border-radius: 1.5em;
  }
  ```
___
**EJEMPLO UTILIZANDO METODOLOGIA BEM:**
  - html
  ```html
  <a href="#" class="button">Botón</a>
  <!-- Al elemento que es tranparente, le agregamos la clase del elemento normal y quedaria con 2 clases  -->
  <a href="#" class="button button--transparent">Botón transparente</a>
  ```
  - css
  ```css
  /* Como podemos ver CON LA METODOLOGIA BEM, las propiedades repetidas se escriben una unica vez, mientras que las que necesitan agregarse o ser cambiadas se sobreescriben abajo*/
  .button{
      display: inline-block;
      padding: 0.5em 1em;
      font-size: 1.2rem;
      text-decoration: none;
      color: azure;
      background-color: royalblue;
      border-radius: 1.5em;
  }
  
  /* Aqui solo colocamos las propiedades que se sobreescriben (por cascada), o que se agregan */
  .button--transparent{
      /* Unicas */
      color: royalblue;
      background-color:transparent;
      border: 1px solid royalblue;
      border-radius: 1.5em;
  }
  ```
___
## Como funciona la metodologia BEM

La metodologia BEM se basa en 3 conceptos principales:

1. **BLOQUES** => Es cualquier elemento autonomo, que podemos reutilizar en cualquier parte de la pagina es un BLOQUE, como:
    - Menú, Logo, Tarjeta, Redes Sociales, ETC...

**EJEMPLO DE BLOQUE:**
  - Cuando tenemos una web, es muy común colocar el logo en el "header" y usar clases especificas para ese logo como **"header-logo"**, lo que nos sugiere **BEM** es que utilicemos clases **"genericas"** como **"logo"** para que pueda ser utilizado en otros sitios.
    ```html
    <!-- Siguiendo esta idea, utilizamos una clase generica que NO esta ligado a ningún sitio especifico del HTML como header o footer -->

    <!-- La clase "logo" NO esta ligada, podriamos reutilizarlo en cualquier sitio de la pagina -->
    <img src="assets/logo.webp" alt="logo" class="logo">
    ```
   
2. **ELEMENTOS** => Son las piezas que conforman (pertenecen) a nuestro bloque como:
    
      - title, text, description, image ETC...

**EJEMPLO DE ELEMENTO:**
  
  - Para nombrar un elemento(la clase):

      - Escribimos el nombre del BLOQUE al que pertenece(Ejemplo: Card)
    
      - 2 guiones bajos(representan elemento BEM)
    
      - Y el nombre que queremos darle al elemento(Ejemplo: title)
```html
<!-- El bloque es CARD -->
  <div class="card">
  <!-- Estos son los ELEMENTOS -->
  <h2 class="card__title">Titulo</h2>
  <p class="card__description">
    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis, alias?
  </p>
  <img src="#" alt="img" class="card__image">
  <!-- Los elementos son nombrados con el nombre del BLOQUE al que pertenecen, y el nombre que uno les da -->


<!-- Si aquí dentro utlizaramos redes sociales NO SERIAN UN ELEMENTO, porque es algo que seguramente reutilizariamos mas adelante, SERIAN UN BLOQUE, y quedaria asi-->

<!-- El bloque es "social-icons" (Si queremos utilizar nuestras redes sociales, lo unico que hacemos es crear nuestra lista y reutilizar clases) -->
  <ul class="social-icons">
    <!-- El resto son elementos PERO de social-icons NO de card -->
    <li class="social-icons__item">
      <a href="#">
        <img src="#" alt="#" class="social-icons__icon">
      </a>
    </li>
    <li class="social-icons__item">
      <a href="#">
        <img src="#" alt="#" class="social-icons__icon">
      </a>
    </li>
    <li class="social-icons__item">
      <a href="#">
        <img src="#" alt="#" class="social-icons__icon">
      </a>
    </li>
  </ul>
</div>

```
3. **MODIFICADORES** => Modifica algún tipo de estilo, SE PUEDEN APLICAR TANTO A BLOQUES COMO A ELEMENTOS.

    - Si queremos modificar, el color de una tarjeta(bloque), o el tamaño un titulo(elemento), ETC...  

**EJEMPLO DE MODIFICADOR:**
  
  - Para nombrar un modificador(la clase de modificación):

      - Escribimos el nombre del BLOQUE al que pertenece(Ejemplo: Card)
    
      - 2 guiones medios(representan modificador BEM)
    
      - Y el nombre que queremos darle al modificador(Ejemplo: blue)

    De esta foma, nuestro elemento o bloque modificado tendria 2 CLASES, la del elemento ORIGINAL, y la del MODIFICADOR

  ```html
  <!-- EJEMPLO SOBRE UN BLOQUE -->
  <!-- Tarjeta original -->
  <div class="card"></div>

  <!-- Tarjeta con MODIFICADOR -->
  <div class="card card--blue"></div>
  <!-- La clase "card" seran los estilos por defecto y la clase "card--blue" la modificación que requiere la tarjeta -->

  <!-- EJEMPLO SOBRE UN ELEMENTO -->
  <!-- Elemento ORIGINAL -->
  <img src="#" alt="#" class="card__image">

  <!-- ELEMENTO CON MODIFICADOR -->
  <img src="#" alt="#" class="card__image card__image--big">

  <!-- Solo haria falta darle estilos en CSS a cada una de las clases -->
  ```
# 2-2 Botones a través de modificadores
Vamos a utilizar botones, que es un ejemplo bastante sencillo, para empezar con BEM.

Tenemos 4 botones de diferentes color todos, SIN la metodologia BEM el codigo de CSS que saldria seria

```css
/* En ningún boton se reutiliza, codigo a pesar de que la mayoria de propiedades son iguales */

.button-blue{
    background-color: royalblue;
    border-radius: .4em;
    color: #fff;
    padding: 0.4em 0.1em;
    border: none;
}

.button-red{
    background-color: firebrick;
    border-radius: .4em;
    color: #fff;
    padding: 0.4em 0.1em;
    border: none;
}

.button-ghost-blue{
    background-color: transparent;
    border-radius: .4em;
    color: royalblue;
    padding: 0.4em 0.1em;
    border: 1px solid royalblue;
}

.button-ghost-red{
    background-color: transparent;
    border-radius: .4em;
    color: firebrick;
    padding: 0.4em 0.1em;
    border: 1px solid firebrick;
}
```

Con la metodologia BEM, BIEN APLICADA, el resultado seria el siguiente:
- html
```html
  <button href="#" class="button button--blue"></button>
  <button href="#" class="button button--red"></button>
  <button href="#" class="button button--ghost-blue"></button>
  <button href="#" class="button button--ghost-red"></button>
```
- css
```css
/* Aca reutilizamos las propiedades que estan compartidas, por lo que el codigo es mucho mas mantenible */
.button{
    border-radius: .4em;
    padding: 0.4em 0.1em;
    border: none;
}

.button--blue,
.button--red{
    color: #fff;
}

.button--blue{
    background-color: royalblue;
}

.button--red{
    background-color: firebrick;
}

.button--ghost-blue,
.button--ghost-red{
    background-color: transparent;
    border: 1px solid currentColor;

}

.button--ghost-blue{
    color: royalblue;
}

.button--ghost-red{
    color: firebrick;
}
```

# 2-3 Menú atraves de elementos

Vamos a hacer un menu muy sencillo para ver como funcionan los elementos dentro de BEM.

1. En este caso el bloque empezaria desde el (ul-"menu"), la clase "main-nav" sirve para colocar estilos QUE NO INTERFIERAN con los del bloque, como estilos de posicionamiento, entre otros.

2. Los elementos "nietos" se nombran exactamente como todos los elementos, unicamente va el nombre del bloque y el nombre que le demos (EJM: menu__link)

- HTML

```html
 <!-- Esto se puede hacer, siempre y cuando los estilos que le demos a "main-nav" no interfieran con el menu (ul), esto es para que el menu se pueda utilizar en otras partes del codigo  -->
 <nav class="main-nav">

  <!-- Para los estilos del menu, comenzamos directamente desde el (ul), este sera nuestro bloque -->
  <ul class="menu">

    <!-- Esta seria la clase de un elemento del bloque "menu" -->
    <li class="menu__item">

      <!-- En el caso del link estaria MAL colocar la clase (menu__item__link) porque el bloque es unicamente "menu", hacer eso seria copiar la estructura html (y esta mal) -->

      <!-- Por lo que la clase de todo lo que pertenezca al bloque sera unicamente el nombre del bloque y el nombre que le demos (EJM: "menu__link") -->
      <a href="#" class="menu__link">Item 1</a>
    </li>
    <li>
      <a href="#" class="menu__link">Item 2</a>
    </li>
    <li>
      <a href="#" class="menu__link">Item 3</a>
    </li>
    <li>
      <a href="#" class="menu__link">Item 4</a>
    </li>
  </ul>
 </nav>
```
- CSS
```css

/* Estas son algunas propiedades que se acostumbra darle a todas las listas o links (No tienen nada que ver nuestra metodologia BEM) */
ul{
    list-style: none;
    padding-left: 0;
    margin-top: 0;
}

a{
    color: aliceblue;
    text-decoration: none;
}

```
- CSS del ejemplo con BEM
```css

/* Desde Aqui establecemos estilos con BEM */

/* Estilos del Bloque */
.menu{
 /* Para este menu no necesitamos especificar estilos de bloque */
}

/* Estilos del elemento Item */
.menu__item{
    /* Para que se coloquen uno al lado del otro (Sin necesidad de flex) */
    display: inline;
}

/* Estilos del elemento Link */
.menu__link{
    margin-right: 1em;
    background-color: royalblue;
    padding: 0.5em 1em;
}
```
En este punto ya tendriamos nuestro menu hecho con la Metodologia BEM, por lo que si deseamos copiar otro menú igual no seria mas que crear en el HTMl, otro menú, identico y ya tendria los mismos estilos.

Pero ahora necesitamos este mismo Menú, PERO EN FORMATO VERTICAL, por lo que debemos usar un modificador, y quedaria de esta forma.

- html

```html
<!-- Este menu lo pegariamos en el lugar que corresponda en nuestro sitio web, (no tendria la clase main-nav porque el menu tendria otra posicion) -->
<nav>
  <!-- El UNICO cambio para hacer este menu vertical de la manera mas eficiente, seria colocar un modificador directamente en el bloque -->
  <ul class="menu menu--vertical">
```
- css 

```css
/* En este caso tenemos que modificar los estilos de los elementos, para esto usamos estilos DESCENDENTES con la clase del modificador (menu--vertical) y solo afectariamos al menu vertical */

.menu--vertical .menu__item{
    /* Con esto ya tenemos el menu en vertical y bien separado */
    display: block;
    margin-bottom: 1.5em;
}

/* Si quisieramos añadir o cambiar cosas a los links del menu vertical, podriamos usar esto */
.menu--vertical .menu__link{
    border-radius: 0.4em;
    background-color: transparent;
}
```
En este caso se usa un solo modificador en el bloque para usar estilos descendentes y poder modificar los elementos. 

Esto es algo que evidentemente aumenta la especifidad (Lo cual habiamos aclarado que NO es recomendable), sin embargo, hay casos como este en que te compensa aumentar la especifidad. Ademas en este caso los estilos del modificador NO SOBREESCRIBEN a los estilos del menú original, precisamente por el mismo modificador.

**NOTA:** A medida de que avancemos el curso vamos a estar utilizar BEM y aprendiendo en que casos es mejor AUMENTAR LA ESPECIFIDAD.

# 2-4 Practica Propuesta

Hacer unas tarjetas con titulo, texto y redes sociales. Usar modificadores para hacer una azul, otra con la imagen mas grande y la ultima azul y con la imagen grande.

# 2-5 Practica Resuelta (Retroalimentación)

1. Resolviendola por mi mismo, me di cuenta que se me dificulto especialmente la colocación de la imagen, aunque si tenia una idea de como era, utilice flexbox que no era necesario y me confundio.

2. Por la parte de BEM, utilice las clases correctamente y bien ejecutadas, lo que me dice que si le entendi a los modificadores y los elementos

3. En el html tambien tuve una confusión colocando un "div" que sobraba precisamente por querer usar flexbox.

4. A medida que pasan los ejercicios me voy dando una idea del correcto funcionamiento de POSITION y en que casos es BUENISIMO usarlo.

5. Tengo que tener en cuenta las ETIQUETAS SEMANTICAS como ARTICLE y no abusar de DIV

En General me gusto que le haya entendido como funciona la metodologia BEM y debo practicar mas el posicionamiento y no ABUSAR de flexbox o grid

# 2-6 Practica Resuelta (Por Dorian)
 
- html
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="/Practica_BEM/styles.css">
  <title>Prueba BEM</title>
</head>
<body>
<main>
  <!-- Tarjeta 1 por defecto -->
  <article class="card">
    <h2 class="card__title">DorianDesings</h2>
    <p class="card__text">Apasionado de las nuevas tecnologias y en especial de CSS y JS. Mi proposito es trasladar mi pasión por enseñar a todos aquellos que quieran aprender de una forma actualizada</p>
    <img class="card__image" src="/Practica_BEM/assets/images/dorian.png" alt="DorianDesings">
    <ul class="social-icons">
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/twitch-logo.png" alt="twitch logo">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/instagram-logo.png" alt="">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/twitter-logo.png" alt="">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/youtube-logo.png" alt="">
        </a>
      </li>
    </ul>
  </article>
  <!-- Tarjeta azul -->
  <article class="card card--blue">
    <h2 class="card__title">DorianDesings</h2>
    <p class="card__text">Apasionado de las nuevas tecnologias y en especial de CSS y JS. Mi proposito es trasladar mi pasión por enseñar a todos aquellos que quieran aprender de una forma actualizada</p>
    <img class="card__image" src="/Practica_BEM/assets/images/dorian.png" alt="DorianDesings">
    <ul class="social-icons">
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/twitch-logo.png" alt="twitch logo">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/instagram-logo.png" alt="">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/twitter-logo.png" alt="">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/youtube-logo.png" alt="">
        </a>
      </li>
    </ul>
  </article>
  <!-- Tarjeta blanca con imagen Grande -->
  <article class="card">
    <h2 class="card__title">DorianDesings</h2>
    <p class="card__text">Apasionado de las nuevas tecnologias y en especial de CSS y JS. Mi proposito es trasladar mi pasión por enseñar a todos aquellos que quieran aprender de una forma actualizada</p>
    <img class="card__image card__image--big" src="/Practica_BEM/assets/images/dorian.png" alt="DorianDesings">
    <ul class="social-icons">
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/twitch-logo.png" alt="twitch logo">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/instagram-logo.png" alt="">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/twitter-logo.png" alt="">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/youtube-logo.png" alt="">
        </a>
      </li>
    </ul>
  </article>
  <!-- Tarjeta azul con imagen Grande -->
  <article class="card card--blue">
    <h2 class="card__title">DorianDesings</h2>
    <p class="card__text">Apasionado de las nuevas tecnologias y en especial de CSS y JS. Mi proposito es trasladar mi pasión por enseñar a todos aquellos que quieran aprender de una forma actualizada</p>
    <img class="card__image card__image--big" src="/Practica_BEM/assets/images/dorian.png" alt="DorianDesings">
    <ul class="social-icons">
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/twitch-logo.png" alt="twitch logo">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/instagram-logo.png" alt="">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/twitter-logo.png" alt="">
        </a>
      </li>
      <li class="social-icons__item">
        <a href="#">
          <img src="/Practica_BEM/assets/images/youtube-logo.png" alt="">
        </a>
      </li>
    </ul>
  </article>
</main>
</body>
</html>
```
- css
```css
*{
    box-sizing: border-box;
}

body{
    margin: 0;
    padding: 2em;
    background-color: #888;
    font-family: sans-serif;
}

ul{
    margin-bottom: 0;
    padding-left: 0;
    margin-top: 0;
    list-style: none;
}

a{
    text-decoration: none;
}

img{
    /* Esto indica que las imagenes no pueden crecer mas que su contenedor */
    max-width: 100%;
}

.card{
    position: relative;
    width: 500px;
    height: 275px;
    margin: 0 auto 1em;
    padding: 1em;
    background-color: #fff;
    border-radius: .7em ;
    -webkit-border-radius: .7em ;
    -moz-border-radius: .7em ;
    -ms-border-radius: .7em ;
    -o-border-radius: .7em ;
    box-shadow: 10px 10px 10px #0003;
}

.card--blue{
    background-color: lightblue;
}

.card__title{
    margin: 0;
    font-size: 2rem;
}

.card__text{
    font-size: .9rem;
    width: 250px;
    line-height: 1.5;
}

.card__image{
    position: absolute;
    bottom: 0;
    right: 1em;
    width: 200px;
}

.card__image--big{
    width: 230px;
}

.social-icons{
    position: absolute;
    bottom: .5em;
}

.social-icons__item{
    display: inline-block;
    width: 45px;
    margin-right: 1em;
}
```
# 3-1 ¿Que son las variables CSS?

*Variables CSS o Custom Properties*

Es un espacio de memoria que almacena un valor, despues usaremos ese valor en todos los sitios necesarios y si en algún momento necesitamos cambiar ese valor, solo tendremos que cambiar el valor de la variable.

Deben ir **SIEMPRE** en un selector (No cuenta con SASS)

- **Sintaxis de una variable:**

    1. Para declararla: --nombre:valor

    2. Para usarla: propiedad: var(--nombre)

Las variables CSS pueden almacenar cualquier **VALOR** válido en CSS, no pueden almacenar ni selectores ni propiedades.

Es importante que sepamos que las variables se almacenan a nivel del DOCUMENTO por lo que tienen herencia y cascada, eso SIGNIFICA que se pueden heredar y que se pueden SOBREESCRIBIR.

Respecto al ámbito(donde las podemos usar) pueden ser:

1. Globales (Accesibles desde cualquier selector)

2. Locales (Accesibles solo desde el elemento donde se declaran)

# 3-2 Declaración y uso de las variables

Las variables se declaran:

1. Con 2 guiones, el nombre que le queremos asignar a la variable y despues el valor.

Las variables se utilizan:

1. Colocamos la propiedad a la que queremos darle el valor de la veriable y la variable asi "var(--nombre)"

**EJEMPLO**

```css
/* Las variables se pueden declarar en el body pero no es buena idea */
body{
    /* Esto es una variable en CSS, si se cambia aqui, cambia todos los colores que  tengan asignada la variable*/
    --text-color:blue;


    /* Aqui se esta utilizando la variable COLOR */
    color: var(--text-color);
    font-family: sans-serif;
}

button,a
{
    /* Aqui tambien utilizamos el color de la variable */
    color: var(--text-color);
}
```
# 3-3 Donde declarar las variables

El sitio correcto para declarar las variables NO es ni en el BODY ni en el HTML, estos son selectores de nivel superior y funcionarian.

PERO por buenas practicas y temas de ESPECIFIDAD las variables se deben DECLARAR en la raíz del documento la cual es la "pseudoClase"(:root), la cual tiene una especifidad de 10.

```css
/* Por temas de buenas practicas y para evitar posibles errores, las variables GLOBALES siempre las vamos a declarar en la pseudoClase (:root) la cual hace referencia a la raiz del documento */

:root{
  --text-color: #fff;
}
```

# 3-4 Fallbacks y soporte a navegadores

## Fallbacks
Los "fallbacks" son como un "PLAN B" en caso de que la variable falle, sea por mal escritura o por que el navegador no lo soporte.

**Colocar un fallback**

Lo hacemos con una "," despues de escribir la variable, y NO hay limite de fallbacks, incluso podriamos usar otra variable de fallback.

```css
/* Declaramos las variable  */
:root{
    --text-color:#fff;
    --text-color-fallback:#000;
}

/* Declaramos los fallbacks, despues de la primera opción */
a{
    color: var(--text-color, var(--text-color-fallback), red);
}
/* Si falla la primera variable, pasara a la variable fallback y si falla pasara al color (red) */
```

## Soporte a navegadores (Que no soportan variables)

Hay una solución que se puede hacer directamente en CSS, sin embargo, NO es la mas optima, porque esto se suele hacer con SASS. 

Pero si lo hacemos solo desde CSS, la solucion que habria,seria declarar primero el color "fallback" y luego sobreescribir con la variable.

**EJEMPLO**

```css
:root{
    --text-color:#fff;
}

a{
    /* Escribimos el primero el color del fallback */
    color: blue;

    /* Luego lo sobreescribimos con la variable */
    color: var(--text-color);
}
/* Los navegadores que entiendan la variable lo van a sobreescribir, los otros pues no */
```

RECORDEMOS que no es la forma mas optima, es mejor hacerlo desde SASS, y esto es solo para dar soporte a navegadores ANTIGUOS

## Importante 

Las variables en CSS son **"KeySensitive"**, por lo que diferencias entre minusculas y mayusculas, la RECOMENDACION es que las variables siempre sean declaradas en minusculas.

# 3-5 Practica Guiada
Nos enseña como colocar la tarjeta que habiamos hecho con BEM, con un modo oscuro y un modo claro

1. Lo primero que hacemos es declarar las variables en ":root"

2. Despues reemplazamos los valores de "background" y "color" del "body" y de "card" por las variables

3. Luego creamos le creamos una clase al "body" que se llame "light" y representara el modo claro 

4. Esta clase hara que cuando el body la tenga, las variables cambien su valor, haciendo que el fondo sea claro y la tarjetas oscuras

5. El resto de codigo es igual
```css
/* Declaramos las variables */
:root{
    --bg-color:#222;
    --bg-card-color: #fff;
    --bg-card-blue-color: lightblue;
    --text-card-color:#000;
}

/* Reemplazamos el valor de background y color por las variables */

body{
    margin: 0;
    padding: 2em;
    background-color: var(--bg-color);
    font-family: sans-serif;
    color: var(--text-card-color);
}

/* Creamos una clase que cambie el valor de las variables para alternar entre modo claro y modo oscuro */

body.light{
    --bg-color:#fff;
    --bg-card-color: #222;
    --bg-card-blue-color: rgb(0, 42, 56);
    --text-card-color:#fff;
}

/* Reemplazamos el valor de background y color por las variables */

.card{
    position: relative;
    width: 500px;
    height: 275px;
    margin: 0 auto 1em;
    padding: 1em;
    background-color: var(--bg-card-color);
    border-radius: .7em ;
    -webkit-border-radius: .7em ;
    -moz-border-radius: .7em ;
    -ms-border-radius: .7em ;
    -o-border-radius: .7em ;
    box-shadow: 10px 10px 10px #0003;
}

/* Reemplazamos el valor de background y color por las variables */

.card--blue{
    background-color: var(--bg-card-blue-color);
}

/* El resto de codigo es igual */
```
# 3-6 Segunda Practica

En esta segunda practica, Dorian quiere que agarremos los botones que hicimos de primeras en BEM y los adaptemos a las variables

*Personalmente yo lo hice con modo claro oscuro, pero la practica de Dorian me gusto arto y es la que vamos a ver*

1. Declaramos las variables del background del boton y el color del boton

2. Asignamos las variables en la clase general de los botones

3. Cambiamos el valor de las variables, en las clases especificas, para que cada boton quede con su color (En los botones normales cambiamos la variable de background, y en los fantasma la variable de color)

4. Para que todos los botones fantasma queden con fondo transparente y borde de color utilizamos un selector de atributo (La primera vez que lo uso)

```css
/* Declaramos las variables */
:root{
    --bg-button-color: #fff;
    --button-text-color: #333;
}

body{
    background-color: #333
}

/* Utilizamos las variables en la clase generica */
.button{
    border-radius: .4em;
    padding: 0.4em 0.5em;
    border: none;
    font-size: 2rem;
    margin-right: 1em;
    background-color: var(--bg-button-color);
    color: var(--button-text-color);
}


/* Utilizamos un selector de atributo (Es la primera vez que lo utilizo) para configurar los estilos generales de los botones fantasma*/
[class*=button--ghost]{
    background-color: transparent;
    border: 1px solid currentColor;
}

/* Cambiamos el valor de la variable segun la necesidad del boton */
.button--blue{
    --bg-button-color: royalblue;
}

.button--red{
    --bg-button-color: red;

}

.button--lime{
    --bg-button-color: lime;
}

.button--ghost-blue{
    --button-text-color: royalblue;
}

.button--ghost-red{
    --button-text-color: red;

}

.button--ghost-lime{
    --button-text-color: lime;
}
```
# 4-1 ¿Que es el Responsive Web Design?

Es un conjunto de técnicas de diseño y desarrollo web que mediante el uso de estructuras flexibles y junto con Media Queries especificados en CSS, logran adaptar un sitio web al dispositivo en el que se ve.

Esto engloba muchas cosas a tener en cuenta, aspecto, experiencia de usuario, multiples dispositivos, optimizaciones de carga usando tanto HTML (por ejemplo, con carga de imágenes especificas a través de la etiqueta picture), como CSS y JavaScript para adaptar el entorno al dispositivo en todos los sentidos. (No es unicamente que se vean bien o que las cosas queden colocadas, sino que solo se carguen los recursos necesarios para cada dispositivo)

en CSS tenemos varias formas de trabajar con el Responsive Design.

## Diferencias entre Diseño WEB y Desarrollo WEB

El DISEÑO WEB es la disciplina que se encarga de estructurar un sitio web en los distintos dispositivos que se va a ver, los diseñadores WEB no tienen que saber codigo ni escribirlo. Su trabajo es diseñar (Prototipos, maquetacion, ETC...)

El DESARROLLADOR WEB son los que agarran esos diseños y los llevan a codigo.

Es posible ser tanto Diseñador, como desarrollador WEB. si uno es bueno en ambos campos se le abren mas oportunidades.

# 4-2 Media Queries (Media Type)

Las Medias queries(Consulta de medios) son útiles cuando deseas momdificar tu pagina web o aplicación en función del tipo o tamaño del dispositivo. (Las media queries van MUCHO mas alla de controlar el ancho de la ventana, podemos controlar el tipo de dispositivo donde se esta ejecutando, para aplicar distintos estilos).

Funcionan como un condicional y en el caso de que se cumpla la condición se aplicarán los estilos.

## Sintaxis 

La sintaxis de una media query, se compone de un "media type" (tipo de medio) que es OPCIONAL y una lista de "media features" (Caracteristicas del dispositivo).

## Media type

Los media type o dispositivos pueden ser:

- **all:** Para todos los dispositivos (Es el valor por defecto).

- _**print:**_ Para medios impresos.

- **screen:** Para pantallas (Es el más comun y el que mas vamos a utilizar).

- **Speech:** Para lectores de pantallas. (Se utiliza para navegadores de texto o apps, diseñadas para INVIDENTES)

**UTILIZACIÓN**

- Para utilizarlo escribimos: @media <|dispositivo|> {Estilos a aplicar} 

```CSS
/* Ejemplo de impresión */
body{
    text-align: center;
    background-color: #222;
    color:lightcoral;
    font-family: sans-serif;
}

@media print{
    /* Aqui dentro colocariamos los estilos que se usarias SI IMPRIMIMOS este sitio web */

body{
    /* Cambia el color de la letra de la pagina a la hora de imprimir*/
    color:red;
}
}
```
Esto no es muy común pero podemos hacerlo cuando es necesario imprimir esa web, y queremos quitar todo lo que no se vea bien en el papel

# 4-3 Media Queries (Media Features)

Los media features o caracteristicas, describen las caracteristicas que debe tener nuestro dispositivo para aplicarse. Aquí incluimos tamaño del dispositivo, preferencias del usuario, si el dispositivo admite hover sobre los elementos o incluso el número de bits por color, entre otras opciones.

**UTILIZACION**

- Para utilizarlo escribimos: @media (Caracteristicas) {Estilos a aplicar}.

Las "media features" mas utilizadas son los breakpoints "puntos de ruptura" donde cambiamos estilos en FUNCIÓN del ancho y/o alto del dispositivo, NO existe ningún estandar que recoja las medidas a utilizar PERO las mas comunes son:

1. Moviles
- 320px
- 340px

2. Tablets
- 720px
- 768px

3. Escritorio
- 1024px
- 1400px (large screen)

Son las mas comunes, aunque pueden cambiar con el tiempo, igualmente DEPENDE MUCHO del tipo de app que estemos haciendo y hacia el tipo de dispositivo que este diseñada.

**IMPORTANTE**

Estos son los que se denominan "major breakpoints", es decir puntos de ruptura IMPORTANTES que cambian en función de las distintas medidas de dispositivos. 

En sitios WEB con una cierta complejidad es habitual que existan "minor breakoints", cambios en un tamaño ESPECIFICO para corregir detalles del maquetado.(Son pequeños cambios que se ajustan a un tamaño muy especifico que de problemas).

## Usar Media Type y Media Feature al tiempo (Operadores logicos)

Su queremos añadir un media type y una media feature en la misma media query tenemos el operador logico **"and"**

- @media screen and (min-width:768px) {estilos a aplicar}

Tambien existen los operadores logicos, **"not"** y **"only"**, pero su uso no es muy común.

```css
/* Debe haber SIEMPRE un espacio antes y despues del operador "and" */
@media screen and (min-width: 768px) {
    body{
        color: red;
    }
}
```
La forma mas recomendable de comprobar que una media query funciona, NO es redimensionar la ventana del navegador

## Comprobar correctamente si una Media query funciona

1. Le damos en la pagina en "inspeccionar"

2. Luego le damos en los telefonos de la parte superior y ya estamos en el evaluador de responsive.

Si tenemos la oportunidad testearlo en diferentes dispositivos, cuantas mas pruebas hagamos, menos margen de error


# 4-4 Etiqueta meta viewport

Esta etiqueta fue creada por apple con el lanzamiento del "Iphone 1" y a dia de hoy aún no existe ningún reemplazo nativo, se estába trabajando en @viewport, pero al final se abandono el proyecto.

Si quitamos esta etiqueta "meta" las media queries dejarán de funcionar, para comprobarlo hay que saber testearlas correctamente

## Atributos de la etiqueta META

Valores que se puede poner al atributo "content" en la etiqueta meta.

[Valores de etiqueta content](https://css-tricks.com/snippets/html/responsive-meta-tag)

El valor que se recomienda usar SIEMPRE es el que viene por defecto el cual es:

(content="width=device-width, initial-scale=1.0")

El resto no los vamos a utilizar practicamente NUNCA, salvo en casos MUY MUY concretos.

Un valor el cual tiene algo de debate es el **"user-scalable"**, que es basicamente si permitimos al usuario hacer zoom en nuestra pagina. acepta 2 valores (yes or no). Es mas recomendable NO utilizar este atributo.

# 4-5 Diseño Adaptativo vs Diseño Responsive

Puede parecer lo mismo pero NO lo es. Ambos enfoques se complementan entre sí, por lo que no hay una forma correcta o incorrecta de hacerlo.

El diseño adaptativo consiste en crear un sitio web para escritorio y otro para movil, puede parecer un enfoque anticuado, pero hay situaciones donde la web movil es tan distinta a la web de escritorio que usar el mismo codigo para las 2 es algo muy complejo y no compensa. (El dominio no es el mismo, como si fueran 2 paginas diferentes)

**IMPORTANTE: Esto NO implica que el sitio web de escritorio NO tenga que ser responsive, también se debe hacer la web de escritorio en su concepto responsive para un ancho reducido**

# 4-6 Mobile First vs Desktop First

En un enfoque **mobile first** se empieza a construir la versión mobile desde el principio y despues se va adaptando el contenido hacia tamaños mas grandes, en el enfoque **desktop first** se hace lo contrario, se empieza por escritorio y se va adaptando el contenido hacia tamaños más pequeños.

Técnicamente, no hay mucha diferencia si un proyecto se inicia desde una pantalla mas pequeña y vamos subiendo el tamaño que si lo hacemos al revés, de pantalla grande a una mas pequeña. Esa es la teoría, PERO en la practica es MUCHO mas facil empezar desde el móvil e ir subiendo, principalmente porque al tener menos sitios para distribuir el contenido, es mejor tomar esa decisión desde el principio.

*las decisiones dificiles, siempre se toman en los sitios pequeños.*

Debemos tener la maquetación de los diseños tanto de escritorio como de movil.

Si queremos usar uno u otro, cambiamos la media query entre "min-width" o "max-width"

**RECOMENDADO: Es mejor 100% Mobile First**

# 4-7 Media Query de Accesibilidad (LightTheme, DarkTheme)

Es muy importante utilizar ESTA media query de ACCESIBILIDAD la cual es:

1. La preferencia que tiene el usuario sobre el Tema Claro y el Tema oscuro, podemos crear temas claros y oscuros en función de las preferencias del usuario (Como tenga el usuario configurado su PC)

```css
@media screen and (prefers-color-scheme:light) {
  body{
    background: #ccc;
  }
}

@media screen and (prefers-color-scheme:dark) {
  body{
    background: #333;
  }
}
```
# 4-8 Elementos Anidados

Es muy común pensar que cuando se habla de responsive todas las medidas deberian ser relativas, porcentajes, unidades de viewport, ETC..., pero esto es falso, en todos los sitios web hay contenido que no necesita escalar ni cambiar de tamaño, en esos casos las unidades absolutas son MUY útiles

SIEMPRE que un elemento no vaya a ESCALAR ni CAMBIAR de tamaño hay que utilizar medidas ABSOLUTAS.

# Links para consultar más información

Ejemplo de diseño responsive

- https://mediaqueri.es/
- https://www.awwwards.com/websites/responsive-design/

Principios básicos del diseño responsive

- https://blog.froont.com/9-basic-principles-of-responsive-web-design/

Libros recomendados

- Responsive web design. Ethan marcotte
- Respons

# 5-1 Propiedad Background
La propiedad background sirve para establecer el contenido y/o comportamiento del fondo de un contenedor.

El fondo de un elemento es el tamaño total del mismo sin incluir el margen. Es decir, el contenido, el padding y el borde.

# 5-2 Background color
Esta propiedad aplica colores sólidos al fondo de un elemento. Admite cualquer código válido en CSS (rgb,hsl,hexadecimal,keywords)

**NOTA:** Cuando le colocamos **'background-color'** al body, se nos pinta TODA la pagina, esto no significa que el body ocupe todo eso, el body puede ocupar mucho menos PERO el CSS interpreta que si le colocamos un **'background-color'** es por que queremos toda la pagina tenga ese color

# 5-3 Background image y background-repeat

## Background image
Esta propiedad sirve para establecer imagenes o degradados al fondo de un elemento. (Nos centraremos acá SOLO en imagenes)

NO es incompatible con **'background-color'**, PERO hay que tener en cuenta que la imagen o el degradado SIEMPRE se colocará por encima del color del fondo.

Para usar una imagen usamos la función **'url()'** y dentro pondremos la ruta donde tenemos nuestra imagen. Podemos utilizar cualquier formato de imagen valido en HTML (jpg, png, webp...)

```css
.box{
    /* La imagen se sobrepondra SIEMPRE al background-color */
    background-image: url(/dorian.png);
    background-color: lightsalmon;
}
```

**NOTA: Cuando la imagen tiene transparencia y el contenedor es muy pequeño, puede que agarremos una parte transparente y pensemos que la imagen no se nos esta viendo, toca ASEGURARNOS bien cambiando el tamaño del contenedor**

### Cuando usar img y cuando background-image
Si la imagen es de adorno y solo esta ahí para verse bonita utilizamos **background-image** si de lo contrario la imagen cuenta algo y es importante para el contexto, usamos **img**

## Background repeat
Esta propiedad controla si la imagen se repetira para rellenar todo el fondo del contenedor. Los valores que admite esta propiedad son:

- **repeat**: (Valor por defecto) se repite la imagen si es necesario para llenar el contenedor 
- **repeat-x**: Repite la imagen horizontalmente
- **repeat-y**: Repite la imagen verticalmente
- **no-repeat**: No repite la imagen

# 5-4 Background-position
Esta propiedad nos permite mover una imagen de fondo dentro de su contenedor, por defecto sus valores son 0 0, que corresponden a la esquina superior izquierda, el primer valor corresponde al eje X y el segundo al eje Y.

Para mover la imagen podemos usar cualquier medida válida en CSS (Lo mas habitual es utilizar px o %), pero si usamos porcentajes hay algo a tener en cuenta, si ponemos `background-position:100% 0` la imagen se colocará a la derecha, alineará el ultimo pixel de la imagen con el ultimo del contenedor.

Tambien tenemos palabras clave que hacen más facil el control de la posición.

- top: equivale al 0% verticalmente.
- right: equivale al 100% horizontalmente.
- bottom: equivale al 100% verticalmente.
- left: equivale al 0% horizontalmente.
- center: equivale a 50% tanto horizontal como verticalmente.

Al colocar palabras clave da igual el orden, es lo mismo poner `top center` que `center top`. ESTO es algo que SOLO funciona si utilizamos palabras clave, al usar valores numericos hay que respetar el orden.

Si colocamos un solo valor en vez de 2, ese valor NO aplicara para cada eje, el eje X tendra el valor que le asignamos y el eje Y tendra el valor `center`. Esto pasa tanto con palabras clave como con valores numericos.

**NOTA: NO es buena idea mezclar valores numericos con palabras clave**

Tambien es completamente posible colocar valores NEGATIVOS, y asi la imagen se saliera del contenedor no genera SCROLL debido a que no ocupa un espacio.

# 5-5 Background-size

Esta propiedad nos permite controlar el tamaño de la imagen de fondo, por defecto su valor `auto` y deja que el navegador calcule las medidas en función del tamaño real de la imagen y la relación de aspecto para no deformar la imagen.

Si queremos establecer la medida manualmente tenemos varias formas de hacerlo.

- **Un valor**: Se aplicara al ancho de la imagen (SIN DEFORMARSE)
- **Dos valores**: El primero sera el ancho y el segundo el alto de la imagen (Se puede deformar)
- **Palabras clave**: 
    - cover: Con este valor la imagen cubrira el contenedor completo sin deformarse, PERO cortando la imagen si fuera necesario.

    - contain: Con este valor la imagen se agrandará todo lo posible hasta que el ancho o alto sea de las mismas medidas que la del contenedor.

# 5-6 Background attachment
Esta propiedad especifica como se comporta el fondo cuando hagamos scroll, hay 3 valores que podemos utilizar:

- **Scroll:** Es el valor por defecto.

- **Fixed:** Hace que el fondo quede fijado al viewport, por lo que aunque hagamos scroll el fondo no se movera. (Si utilizamos este valor, la imagen se posicionara respecto al viewport y NO al contenedor, esto pasara tanto con `background-position` como con `background-size`)

- **Local:** Si tenemos contenido con scroll en un contenedor hará que la imagen de fondo se mueva junto con el scroll. (Si la imagen es muy grande y tenemos scroll a medida que hacemos scroll la imagen se descubrira)

# 5-7 Efecto parallax
Es un efecto puramente decorativo que se ve muy bonito, se ve muy parecido a las paginas de producto de dji o similar
```css
/* Podemos tener las cajas que queramos, las cajas van a tener imagenes */
.box{
    min-height: 100vh;
    /* este padding es para evitar el colapsado de margenes */
    padding: 1px;
    /** Con es attachment conseguimos el efecto parallax que consta en que las imagenes parecieran estaticas mientras otra se mueve, la verdad se ve muy bonito */
    background-attachment: fixed;
}

/* Caja de texto dentro de las cajas grandes */
.box-texts{
    margin-top: 40vh;
    background-color: rgb(0 0 0/ 0.4);
    color: aliceblue;
    padding: 1em 2em;
    width: 80%;
    margin-left: auto;
    margin-right: auto;
}

.box-1{
    /* Escogemos las imagenes de cada una de las cajas */
    background-image: url();
}

.box-2{
    /* Escogemos las imagenes de cada una de las cajas */
    background-image: url();
}

.box-3{
    /* Escogemos las imagenes de cada una de las cajas */
    background-image: url();
}
```
# 5-8 Background origin y background clip

## Background origin
Esta propiedad define en que zona del box-model se empieza a pintar el fondo.

**Esta propiedad sólo funciona cuando usamos background-image**

Tenemos 3 valores posibles.

- **border-box:** El fondo empieza a pintar desde la esquina izquierda superior del contenedor.
    - La imagen empieza desde el borde

- **padding-box:** *Valor por defecto*. El fondo se empieza a pintar desde la esquina superior izquierda de la zona que corresponga al padding.
    - Es el valor normal, ignora el borde

- **content-box:** El fondo se empieza a pintar desde la esquina superior izquierda de la zona que corresponda al contenido 
    - Ignora el padding y se dibuja despues de este

## Background clip
Esta propiedad define en que zona del box-model se pinta el fondo. Tenemos 3 valores posibles.

- border-box: *Valor por defecto*. rellenará todo el box-model.

- padding-box: Rellanará desde el contenido hasta el padding.

- content-box: Rellenará sólo la parte que corresponda al contenido

Estas 2 propiedades no se suelen utilizar mucho, pero esta bueno saberlas por si acaso

# 5-9 Background multiples
Como trabajar con multiples backgrounds.

1. Si queremos poner mas backgrounds los tenemos separar por `,`

2. El orden de dibujado es muy importante, la que este mas arribe SIEMPRE sera la PRIMERA que pongamos

```css
.ejemplo{
    /* Podemos colocar las imagenes que queramos separadas por `,`  */
    background-image: url(primera),url(segunda),url(tercera);


    /* Para dar propiedades es el mismo principio */
    /* Primera, segunda, etc... */
    background-size: 50%,25%;
    background-position: bottom right,bottom left;
}
```
# 5-10 Background Shorthand
Si utilizamos la propiedad background podemos asignar multiples propiedades en una sola linea.

Estas son todas las que podemos declarar

`background: image position/size repeat attachment origin clip color;`

NO es necesario declarar todos los valores en la declaración, pero hay que recordar cuales son los valores por defecto de las propiedades que no declaremos:

- `background-image: none;`
- `background-position: 0 0;`
- `background-size: auto;`
- `background-repeat: repeat;`
- `background-attachment: scroll;`
- `background-origin: padding-box;`
- `background-clip: border-box;`
- `background-color: trasparent;`

Todas las que no pongamos tendran su valor por defecto

El orden de las propiedades por norma general no importa, PERO hay 3 normas que no nos podemos saltar:

- `background-origin` y `background-clip` deben declararse en el orden correcto. Esto se debe a que pueden compartir un mismo valor, si sólo ponemos un valor se aplicará a las 2 propiedades, si ponemos 2 valores, el PRIMERO será para `background-origin` y el SEGUNDO para `background-clip`

- `background-size` se debe declarar inmediatamente después de `background-position` y ambas propiedades deben estar separados por una barra `/`.

- Si se utiliza el shorthand para declarar multiples background solo el ultimo podra tener la propiedad `background-color`

**EJEMPLO FINAL**
```css
/* bottom right (position) y contain(size) DEBEN ir juntas */
    background: no-repeat url(imagen.jpg) bottom right / contain lightblue;
```
**NOTA: Personalmente a mi me gustan mas declararlas por SEPARADO**
