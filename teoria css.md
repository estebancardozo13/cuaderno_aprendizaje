# 1. Conectar CSS a HTML

## 1. La forma mas recomendada y la mas usada

```HTML
<link rel="stylesheet" href="/conectar html y css/css/styles.css">
```

Con esta forma tenemos el CSS en un archivo aparte y podemos usarlo en mas de un archivo, a demas de ser una buena practica tener estos 2 por separado

## 2. La forma menos usual (NO tan recomendada)

```HTML
<style>
    /* Aqui dentro va el CSS */
</style>
```

Es una forma posible pero NO tan recomendada, por las pocas facilidades que brinda, sin embargo hay casos muy especificos donde se debera usar

## 3. Existen otras 2 formas que no se deben utilizar NUNCA

1. El CSS directamente en las etiquetas (Es una mala practica).

2. Usar "@import" JAMAS se debe hacer debido a que se carga el CSS de forma asincrona.

# 2. Sintaxis de CSS

- Selector : Elemento a aplicar estilos
- Propiedad : Lo que vamos a cambiar
- Valor : El valor que le damos a la propiedad
- Declaración : propiedad + valor
- Regla: Selector + Valor

```CSS
/* REGLA */
selector {
    /* DECLARACIONES */
    propiedad: valor;
    propiedad2: valor;
    propiedadN: valor;
}

/* Ejemplo */
body {
    background-color: red;
}
```

# 3. Selectores

Existen en CSS:

- ## Selectores simples

  - ### Selectores Elementales

    - Selector Universal ==> (\*)

    ```css
    /* Se encarga de seleccionar TODO se utiliza para cosas muy concretas y es mejor no usarlo */

    * {
      background-color: red;
    }
    ```

    - Selector de tipo o etiqueta ==> (_Nombre de la etiqueta_)

    ```css
    /* Es sencillamente colocar el nombre de la etiqueta */

    h1 {
      background-color: lightcyan;
    }
    p {
      background-color: green;
    }
    ```

  - ### Selectores de Atributo

    - id ==> (id del elemento)

    ```css
    /* Colocamos el id del elemento despues de un # -- No es recomendable dar estilos con ID*/

    #title {
      background-color: green;
    }
    ```

    - clase ==> (clase del elemento)

    ```css
    /* Colocamos la clase despues de un (.)*/

    .title {
      background-color: salmon;
    }
    ```

    - Otros atributos.

    ```css
    /* Para colocar otros atributos los colocamos entre llaves asi: [atributo]*/

    [href] {
      background-color: red;
    }

    /*Tambien podemos colocar el atributo + valor (Si el valor coincide se va a aplicar)*/

    [href="https://google.com"]
    {
      background-color: red;
    }

    /*Para comprobar si el atributo "empieza" por ese valor usamos: */

    [href^="color"] {
      background-color: red;
    }

    /* Comprueba que el valor coincida sin importar en que posición este*/

    [href*="color"] {
      background-color: red;
    }

    /*Para comprobar si el atributo "termina" por ese valor */

    [href$="red"] {
      background-color: red;
    }
    ```

- ## Selectores compuestos

  - Selectores Agrupados

  ```css
  /*Si queremos ponerle a varios elementos un mismo atributo lo podemos hacer de esta forma para no estar repitiendo codigo*/

  .text,
  .text-2,
  .text-3,
  .text-4 {
    background-color: green;
  }
  ```

  - Selectores Combinadores

    - Selector Descendiente

    ```css
    /*Es como darle una "ruta" de los elementos que queremos darle estilo*/

    div .title-2 {
      background-color: red;
    }

    /*Le podemos dar el nivel de descendencia que queramos, pero no es recomendable ni buena practica bajar mas de 2 niveles*/
    ```

    - Selectores Hermanos

    ```css
    /*Sirve para seleccionar un elemento atraves de un elemento hermano EJ= ("elemento hermano" + elemento a seleccionar)*/

    .text-2 + .title-2 {
      background-color: tomato;
    }
    /*Solo se modifica el hermano*/

    /* y es UNICAMENTE el hermano SIGUIENTE, o TODOS los hermanos SIGUIENTES*/

    /*Selecciona todos los hermanos siguientes que sean P en este ejemplo*/
    .text-2 ~ p {
      background-color: red;
    }
    ```

    - Selector de Hijo Directo

    ```css
    /* Si queremos una selección mas precisa, agarrando solamente los hijos directos */

    .container > p {
      background-color: tomato;
    }
    ```

  - Pseudo Clases (Lo veremos mas adelante)
# 4. Especifidad y cascada (IMPORTANTE)
Establece como de especifico es un selector, para saber que estilo aplicar.

Establece que tan ESPECIFICO debe ser el selector, para saber que estilo aplicar

 **EJ**: Si tengo varios selectores con varios valores que apuntan al mismo elemento asi: 
 ```css
 /*Todos los selectores apuntan al mismo elemento (H1)*/
 
 /*Este es el estilo que se aplica por encima de todos porque su espcifidad es la mayor*/

 h1.title#title{ /*(1,1,1)*/
     background-color:tomato; 
 }

 h1 { /*(0,0,1)*/
     background-color: red;
 }

 .title{ /*(0,1,0)*/
    background-color: blue; 
 }

 #title{ /*(1,0,0)*/
    background-color: green; 
 }

 h1.title{ /*(0,1,1)*/
    background-color: yellow;
 }
 ``` 
Se aplica el estilo con mayor NUMERO de especifidad, la especifidad son la suma de los valores de los elementos, y el valor es asi: 

* Etiquetas y Pseudoelementos = 001
* Clases, atributos y Pseudoclases = 010
* IDs = 100 
* Estilos en linea = 1000 (Los que se ponen en HTML)

Esto es la causa de que unos selectores se apliquen por encima de otros (HAY QUE TENERLO EN CUENTA). 

```CSS
/*Valor "!important" le gana a cualquier especifidad, pero NO SE DEBE USAR JAMAS*/

h1{
    background-color: red !important; 
}

```

Tambien existe el valor **!important** que si es colocado le gana por encima de cualquier especifidad, PERO NO SE DEBE USAR NUNCA

* Si la especifidad ES LA MISMA, si se va a sobre escribir el codigo (Es decir la CASCADA SI VA A FUNCIONAR)

# 5. Como saber si tengo escrito un buen CSS 
En esta pagina podremos evaluar el CSS, los lineamientos para que sea bueno es que debe empezar con una especifidad baja (Desde el piso la linea) y subir un poco y mantenerse. Entre mas plana este la linea del grafico mejor es el CSS, lo importante es no tener picos. 

[Evaluador de CSS](https://jonassebastianohlsson.com/specificity-graph/)

Los picos son malos, y la especifidad va aumentando, a medida que el CSS va avanzando

# 6. Herencia en CSS
Es la capacidad que tienen algunos elementos de HEREDAR capacidades de sus elementos CONTENEDORES
```html
<!-- la etiqueta "span" hereda las propiedades que tiene "h1" -->
<h1 id="title" class="title">Fundamentos de <span>CSS</span></h1>
```
* Hay muchas propiedades y etiquetas que permiten heredar
  * Las propiedades de "color" y "font-size" heredan casi siempre.

* Las etiquetas "a" (Los Enlaces), NO heredan propiedades, ellas manejan su propio estilo.

* ## Si queremos FORZAR LA HERENCIA

  usamos el valor "inherit" en la propiedad a heredar del selector HIJO :
    ```css
     /* Si queremos FORZAR la herencia de alguna propiedad en especifico, por ejemplo de los enlaces podemos hacer lo siguiente */

    /* El enlace (.link) esta DENTRO de un parrafo (.text) y queremos que herede el color del parrafo */

    .text{
      color: red;
    }

    /*Este enlace recibira el color del padre, por el valor "inherit" en la propiedad "color" */

    .link{
      color:inherit;
    }
    ```

* ## Si queremos FORZAR la NO HERENCIA (Que no se aplique la herencia)
Usamos el valor "initial" en la propiedad que NO queremos HEREDAR del selector HIJO:
```css
/* Si queremos FORZAR a un elemento que NO HEREDE de su PADRE una propiedad en especifico, por ejemplo una lista, podemos hacer lo siguiente */

/* Los items de la lista (.list) tienen un color, pero queremos que un item especifico (.list-especific) NO HEREDE ese color  */

.list {
   color:indianred;
}

/* Para que no herede, colocamos en la propiedad que esta heredando, el valor "initial" que coloca ese propiedad en su estado inicial, SIN HERENCIA*/

.list-especific {
   color:initial;
}
```
# 7. Estilos computados (IMPORTANTE)
Es una de las herramientas mas utiles para entender nuestro CSS. Estamos hablando de las herramientas de desarrollo de los navegadores (Inspeccionar)

* En la parte de la izquierda vemos el HTML que hemos contruido, tal cual lo escribimos

* En la zona derecha en la pestaña "Styles" nos mostrara el codig CSS que tienen los elementos HTML, por ejemplo si clickeo un elemento HTML de la izquierda, en la derecha me aparecera su CSS
  * Aperecera los estilos que nosotros le hayamos colocado, y los que estan por defecto en el navegador "user agent"

## Pestaña computed
Nos muestra todas las propiedades que se le han aplicado a cada elemento y el PORQUE se le han aplicado, asi podemos saber si algo no se aplica por temas de especifidad o cascada

Es importante saber interpretar las pestañas para que saber porque y como se aplican los estilos (ES MUY UTIL), es el primer sitio para investigar


# 8. Estilos del Navegador
  Los estilos por defecto pueden cambiar en cada Navegador, aquí entra la relevancia de "NORMALIZAR los estilos", para que la pagina tenga consistencia en cualquier navegador.

  Para normalizar los estilos POR DEFECTO de todos los navegadores, hasta el momento la MEJOR FORMA (Desde el punto de vista de Dorian), es por medio del archivo normalize, que lo puedes descargar aquí, hay otras formas pero dice que este es el mejor 

  [Normalize](https://necolas.github.io/normalize.css/)

  Este archivo es una hoja de CSS, que la puedes adjuntar a tus proyetos como cualquier otro CSS.

  **TENER EN CUENTA: Se debe colocar de primeras en el HTML, para que la cascada funcione correctamente y no AFECTE nuestros estilos.**

  Basicamente lo que hace esta hoja es estandarizar los estilos por defectos de los navegadores para que nuestra web se vea igual en todos ellos.

  Es importante porque asi partimos desde el mismo punto de inicio para cada navegador
  ```html
    <link rel="stylesheet" href="/normalize.css">
  ```

# 9. Prefijos Propietarios
Cuando una propiedad CSS, se convierte en un estandar o se comienzan las pruebas, los navegadores tienen que implementarla, de lo contrario se generaran problemas.

Pero mientras la propiedad es implementada nativamente por los navegadores, se deben usar ciertos prefijos para que el navegador sea capaz de interpretarla y no genere problemas.

Para colocar los prefijos que hacen falta, hay varias herramientas, en el caso de VSC, esta autoprefixer o css-prefixer...

EJEMPLO:

```css
/*Propiedad que no esta totalmente adaptada en todos los navegadores "transform" */
.ejemplo{
  transform: valor;
}
/*Prefijos necesarios para su compatibilidad, dependiendo de las versiones a las que necesitemos llegar*/
.ejemplo{
   transform: valor;
   -webkit-transform: valor;
   -moz-transform: valor;
   -ms-transform: valor;
   -o-transform: valor;
}
```
# 10. Box Model
![Modelo de una caja](/assets/recursos_teoricos/box%20model.png)

* Padding => Es el relleno DENTRO de la caja 
* Margin => La distacia entre una caja y otra 
* Width & Height => Ancho y alto de la caja

# 11. Width & Height
* El ANCHO y ALTO unicamente funcionan en elementos de BLOQUE
* Los elementos de linea no tienen medidas, el tamaño lo determina UNICAMENTE su CONTENIDO

```css
/*El alto y el ancho funcionan unicamente para elementos de bloque*/
.block {
   background-color: purple;
   width: 200px;
   height: 200px;
}

/*!Los Elementos en linea NO tienen Medidas. El tamaño lo determina UNICAMENTE su contenido*/
.inline {
   background-color: lightcoral;
   color: inherit;
  
   width: 200px;
   width: 200px;
}
```
# 12. Margin
## Elementos en bloque
Es la propiedad que nos permite generar espacio entre elementos.

Es un shortHand (Propiedad abreviada) que controla los 4 lados posibles a los que se les puede dar margener:
* **margin-top:** Margen Superior
* **margin-right:** Margen Derecho
* **margin-bottom:** Margen Inferios
* **margin-left:** Margen Izquierdo

Admite hasta 4 valores que representan esto:
* 1 Valor: top/right/bottom/left;
* 2 Valor: top/bottom - left/right;
* 3 Valor: top - left/right - bottom;
* 4 Valor: top - right - bottom - left;
```css
.ejemplo{
  /*Todos los lados*/
   margin: 20px;
   /*arriba/abajo - laterales*/
   margin: 20px 10px;
   /*Arriba - laterales - abajo*/
   margin: 20px 10px 5px;
   /*Arriba - derecha - abajo - izquierda*/
   margin: 20px 10px 5px 0px;
}
```
## Elementos en linea

* Los elementos en linea unicamente tienen Margin LATERALES, los margin de arriba y abajo no les afecta en nada

## Trucos del Margin (Auto)
* Cuando tenemos elementos de BLOQUE, podemos mover ese bloque usando margenes automaticos
  * Para esto se debe tener un "width" declarado, de lo contrario ocupara todo el espacio lateral y no servira el margen
```css
   /* Con esto pegamos el elemento a la izquierda */
   margin-right: auto;

   /* Con esto pegamos el elemento a la derecha */
   margin-left: auto;

   /*Para centrar un elemento haremos esto*/
   margin-left: auto;
   margin-right: auto;
```
## Errores al usar Margin
1. **Dorian Desings**, dice que desde el punto de vista de él, usar el selector universal para poner "margin" y "padding" en 0, es una mala practica, puesto que tocaria reestablecer margenes elemento por elemento, lo que hace perder tiempo. (Aunque en el 99% de las veces se hace)

    Él lleva 9 años usando CSS y no le parece   util 
    ```css
    /*Segun él NO HACERLO*/
    * {
       margin: 0;
       padding: 0;
    }
    ```
2. Para centrar un elemento utilizar "margin: 0 auto;"
    ```css
    /*Es malo hacerlo porque reescribe las margenes superiores e inferiores NO HACERLO*/
    margin: 0 auto;

    /*Si queremos centrar unicamente horizontalmente usamos esto, y no tocamos margenes que no se deben*/
    margin-left: auto;
    margin-right:auto;
    ```
## Margin Recomendado
* Lo que si es recomendado es colocarle al body un "margin : 0;" porque asi los menús y otras cosas pueden quedar bien pegados al navegador
    ```css
    body{
      margin:0;
    }
    ```
* Cada cosa que escribamos, SEPAMOS porque la escribimos, no solamente escribamosla porque si

# 13. Padding
Es la propiedad que nos permite generar espacio interno entre el borde y la caja (Relleno). Es tambien un ShortHand y controla 4 lados posibles.
```css
.ejemplo{
  /*Todos los lados*/
   margin: 20px;
   /*arriba/abajo - laterales*/
   margin: 20px 10px;
   /*Arriba - laterales - abajo*/
   margin: 20px 10px 5px;
   /*Arriba - derecha - abajo - izquierda*/
   margin: 20px 10px 5px 0px;
}
```
## Elementos de Bloque
Funciona correctamente el padding, como se supone que deberia.

## Elementos de Linea
En este caso el "Padding" SI FUNCIONA Correctamente, para todos sus lados

## NOTA: Cuando utilizar PADDING y cuando utilizar MARGIN
Definamos lo que queremos, si queremos separar el contenido y aumentar el tamaño de la caja, del borde de la caja usarmos "PADDING", si mi objetivo es separar entre caja y caja mejor uso "MARGIN"

# 14.Border
Es la propiedad que nos permite modificar el borde de la caja. Es un shorthand pero de 3 propiedades
```css
border-width: ancho borde;
border-style: estilo borde;
border-color: color borde;
/* ShortHand: width-style-color*/
border: 20px solid red;
```
* A su ves las propiedades width-style-color, TAMBIEN SON SHORTHAND, que controlan cada uno del lado de los bordes, Top-Right-Bottom-Left
```css
/*Algunos ejemplos*/
border-top-style: Estilo de arriba;
border-bottom-color: Color de abajo;
border-left-color: Ancho de la izquierda 
```
## Valores de Border-Style 
Listado de valores para style:
```css
.ejemplo{
    /* Quita los bordes */
    border-style:none;

    /* Esconde los bordes (hay una pequeña diferencia con el anterior) */
    border-style: hidden;

    /* Hacer un borde hecho con puntos */
    border-style: dotted;

    /* Hacer un borde con lineas */
    border-style: dashed;

    /* Hacer el borde NORMAL (El mas utilizado) */
    border-style: solid;

    /* Hacer borde con doble linea */
    border-style: double;

    /* Hacer un borde en "3d" con sombra (cambia las sombras)*/
    border-style: groove;
    border-style: ridge;

    /* Hacer un borde plano, con sombra (Cambia las sombras) */
    border-style: inset;
    border-style: outset;
}
```
# 15.Box Sizing
Es la propiedad que nos permite modificar el CALCULO que hace el navegador a la hora de modificar las propiedades content, padding, y border.

Recibe 2 valores: 
* content-box => Valor por defecto
* border-box => Calculo de tamaño del elemento incluyendo el padding y el border

Es decir, si queremos que una caja mida un tamaño determinado, incluyendo el padding que pueda tener y el border, utilizamos "border-box", de lo contrario la caja medira cierto valor y sobre ese se le sumara el tamaño del padding y border.

## BUENA PRACTICA DE SELECTOR UNIVERSAL
Como casi siempre queremos que el navegador re calcule el tamaño por nosotros, utilizamos el SELECTOR UNIVERSAL para definir "box-sizing: border-box;"
```css
*{
  box-sizing: border-box;
}
```
# 16. Border Radius Circular
Es la propiedad que nos permite redondear vertices de forma INDEPENDIENTE 

1. Es un shorthand y funciona como tal 
    ```css
    .ejemplo {
        border-top-left-radius: x;
        border-top-right-radius: x;
        border-bottom-left-radius: x;
        border-bottom-right-radius: x;
    }
    ```
2. Si solo recibe un valor dibujara solo un circulo con el radio que le indiquemos, de esa forma se podria redondear las esquinas de forma conjunta o independiente 

# 17. Border Radius Eliptico
Con "Border Radius" tambien tenemos la posibilidad de dibujar una elipse, esto se hace asignandole 2 radios a cada vertice.
```css
.ejemplo{
  /* El primero sera para el eje X y el otro para el eje y */
    border-top-left-radius: 50px 100px;
}
```
Si lo que queremos es que todos los vertices de nuestra caja tengan la misma vertice, lo hacemos de la siguiente manera.
```css
/* Dibujara 4 elipses con 50 en el eje X y 100 en el eje Y*/
.ejemplo{
    border-radius: 50px / 100px;
    -webkit-border-radius: 50px / 100px;
    -moz-border-radius: 50px / 100px;
    -ms-border-radius: 50px / 100px;
    -o-border-radius: 50px / 100px;
}
```
Y si queremos hacer los elipses diferentes en cada vertice con una sola linea haremos esto (Al principio es complicado pero es posible)
```css
.ejemplo{
    /* Asi haremos en cada vertice diferentes elipses, la primer elipse corresponde al PRIMER VALOR en el eje X con el PRIMER VALOR DESPUES DE "/" en en eje Y y asi respectivamente  */

    /* A la izquierda los radios en el eje X y a la derecha los radios en el eje Y */

    border-radius:100px 200px 300px 400px / 400px 300px 200px 100px ;
}
```
* NOTA: Existe una propiedad mas para "Border-Radius" llamada "Border-Image" PERO aún no la veremos

# 18. OverFlow
*Decimos que un contenido se desborda, cuando la caja es mas pequeña que el contenido*

Overflow es la propiedad que utlizamos para contener el desbordamiento de las cajas, controlamos el desbordamiento del contenido, tenemos 4 valores para OverFlow:
* visible (valor por defecto, seguiria igual)
* hidden (Se esconde el desborde)
* Scroll (Aparece la barra para hacer Scroll)
* Auto (El mas recomendado Aparece la barra de Scroll SOLO SI HACE FALTA)

OverFlow contempla el eje X y el eje Y aunque no es muy normal, asignarlos por separado (Pero se puede)
 ```css
 .ejemplo {
    overflow: auto;
    overflow: hidden;
    overflow: scroll;
    /* Lo mismo que no ponerlo */
    overflow: visible;
}
 ```
 Overflow nos puede servir demasiado a la hora de dar diseño a nuestra web, es IMPORTANTE

# 19. Colapsado de Margenes
## Problema 1 - Margin-bottom con Margin-top
Es como un fallo de CSS y es que los margenes "Se unen" entonces no da bien el margen que deseamos EL MARGEN VERTICAL ES EL QUE COLAPSA

**EJEMPLO: Si tenemos un margin-bottom para una caja y un margin-top para otro, los margenes se "unen(solapan)" y solo queda el margen mas grande y no se separan lo que deberian**

* Este es un problema que no tiene solución, entonces la recomendación es ir empujando los elementos hacia abajo (No juntar margin-bottom con margin-top, porque sera un dolor de cabeza)

* Solo sucede con los margenes verticales, los horizontales NO SE UNEN y se separan CORRECTAMENTE

## Problema 2 - Margen entre padres e hijos
Cuando un hijo tiene un margen y por defecto arrastra al padre (Lo descuadra)- NO TIENE SOLUCIÖN peor hay truco para arreglarlo
```css
/* El elemento padre debera tener alguna de estas 3 opciones */
.ejemplo{
  overflow:hidden;
  padding-top:0.1px;
  border-top:0.1px solid #color;
}
```
Con alguna de estas 3 opciones evitamos que el margen del hijo arrastre al elemento del padre

# 20. Display
Nos sirve para cambiar el contexto dentro del navegador, es decir si tenemos elementos de bloque o elementos de linea, podemos modificar su comportamiento con display

Admite varios valores:
* none => Hace que el elemento no se muestre, pero siga cargandose (Lo esconde a la vista, pero ocupa espacio)

* block => Hace que el elemento sea de bloque (Se convierte en un elemento de bloque)

* inline => Hace que el elemento sea de linea (Lo convierte en un elemento de linea)

* inline-block => Hace que el elemento sea de linea pero admite medidas y margenes verticales (El elemento sera de linea PERO ahora podemos colocarle Margenes y medidas como un elemento de BLOQUE)

* HAY MAS PERO NO LAS VAMOS A VER AÚN