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

h1.title#title {
  /*(1,1,1)*/
  background-color: tomato;
}

h1 {
  /*(0,0,1)*/
  background-color: red;
}

.title {
  /*(0,1,0)*/
  background-color: blue;
}

#title {
  /*(1,0,0)*/
  background-color: green;
}

h1.title {
  /*(0,1,1)*/
  background-color: yellow;
}
```

Se aplica el estilo con mayor NUMERO de especifidad, la especifidad son la suma de los valores de los elementos, y el valor es asi:

- Etiquetas y Pseudoelementos = 001
- Clases, atributos y Pseudoclases = 010
- IDs = 100
- Estilos en linea = 1000 (Los que se ponen en HTML)

Esto es la causa de que unos selectores se apliquen por encima de otros (HAY QUE TENERLO EN CUENTA).

```CSS
/*Valor "!important" le gana a cualquier especifidad, pero NO SE DEBE USAR JAMAS*/

h1{
    background-color: red !important;
}

```

Tambien existe el valor **!important** que si es colocado le gana por encima de cualquier especifidad, PERO NO SE DEBE USAR NUNCA

- Si la especifidad ES LA MISMA, si se va a sobre escribir el codigo (Es decir la CASCADA SI VA A FUNCIONAR)

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

- Hay muchas propiedades y etiquetas que permiten heredar

  - Las propiedades de "color" y "font-size" heredan casi siempre.

- Las etiquetas "a" (Los Enlaces), NO heredan propiedades, ellas manejan su propio estilo.

- ## Si queremos FORZAR LA HERENCIA

  usamos el valor "inherit" en la propiedad a heredar del selector HIJO :

  ```css
  /* Si queremos FORZAR la herencia de alguna propiedad en especifico, por ejemplo de los enlaces podemos hacer lo siguiente */

  /* El enlace (.link) esta DENTRO de un parrafo (.text) y queremos que herede el color del parrafo */

  .text {
    color: red;
  }

  /*Este enlace recibira el color del padre, por el valor "inherit" en la propiedad "color" */

  .link {
    color: inherit;
  }
  ```

- ## Si queremos FORZAR la NO HERENCIA (Que no se aplique la herencia)
  Usamos el valor "initial" en la propiedad que NO queremos HEREDAR del selector HIJO:

```css
/* Si queremos FORZAR a un elemento que NO HEREDE de su PADRE una propiedad en especifico, por ejemplo una lista, podemos hacer lo siguiente */

/* Los items de la lista (.list) tienen un color, pero queremos que un item especifico (.list-especific) NO HEREDE ese color  */

.list {
  color: indianred;
}

/* Para que no herede, colocamos en la propiedad que esta heredando, el valor "initial" que coloca ese propiedad en su estado inicial, SIN HERENCIA*/

.list-especific {
  color: initial;
}
```

# 7. Estilos computados (IMPORTANTE)

Es una de las herramientas mas utiles para entender nuestro CSS. Estamos hablando de las herramientas de desarrollo de los navegadores (Inspeccionar)

- En la parte de la izquierda vemos el HTML que hemos contruido, tal cual lo escribimos

- En la zona derecha en la pestaña "Styles" nos mostrara el codig CSS que tienen los elementos HTML, por ejemplo si clickeo un elemento HTML de la izquierda, en la derecha me aparecera su CSS
  - Aperecera los estilos que nosotros le hayamos colocado, y los que estan por defecto en el navegador "user agent"

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
<link rel="stylesheet" href="/normalize.css" />
```

# 9. Prefijos Propietarios

Cuando una propiedad CSS, se convierte en un estandar o se comienzan las pruebas, los navegadores tienen que implementarla, de lo contrario se generaran problemas.

Pero mientras la propiedad es implementada nativamente por los navegadores, se deben usar ciertos prefijos para que el navegador sea capaz de interpretarla y no genere problemas.

Para colocar los prefijos que hacen falta, hay varias herramientas, en el caso de VSC, esta autoprefixer o css-prefixer...

EJEMPLO:

```css
/*Propiedad que no esta totalmente adaptada en todos los navegadores "transform" */
.ejemplo {
  transform: valor;
}
/*Prefijos necesarios para su compatibilidad, dependiendo de las versiones a las que necesitemos llegar*/
.ejemplo {
  transform: valor;
  -webkit-transform: valor;
  -moz-transform: valor;
  -ms-transform: valor;
  -o-transform: valor;
}
```

# 10. Box Model

![Modelo de una caja](/assets/recursos_teoricos/box%20model.png)

- Padding => Es el relleno DENTRO de la caja
- Margin => La distacia entre una caja y otra
- Width & Height => Ancho y alto de la caja

# 11. Width & Height

- El ANCHO y ALTO unicamente funcionan en elementos de BLOQUE
- Los elementos de linea no tienen medidas, el tamaño lo determina UNICAMENTE su CONTENIDO

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

- **margin-top:** Margen Superior
- **margin-right:** Margen Derecho
- **margin-bottom:** Margen Inferios
- **margin-left:** Margen Izquierdo

Admite hasta 4 valores que representan esto:

- 1 Valor: top/right/bottom/left;
- 2 Valor: top/bottom - left/right;
- 3 Valor: top - left/right - bottom;
- 4 Valor: top - right - bottom - left;

```css
.ejemplo {
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

- Los elementos en linea unicamente tienen Margin LATERALES, los margin de arriba y abajo no les afecta en nada

## Trucos del Margin (Auto)

- Cuando tenemos elementos de BLOQUE, podemos mover ese bloque usando margenes automaticos
  - Para esto se debe tener un "width" declarado, de lo contrario ocupara todo el espacio lateral y no servira el margen

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

   Él lleva 9 años usando CSS y no le parece util

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
   margin-right: auto;
   ```

## Margin Recomendado

- Lo que si es recomendado es colocarle al body un "margin : 0;" porque asi los menús y otras cosas pueden quedar bien pegados al navegador
  ```css
  body {
    margin: 0;
  }
  ```
- Cada cosa que escribamos, SEPAMOS porque la escribimos, no solamente escribamosla porque si

# 13. Padding

Es la propiedad que nos permite generar espacio interno entre el borde y la caja (Relleno). Es tambien un ShortHand y controla 4 lados posibles.

```css
.ejemplo {
  /*Todos los lados*/
  padding: 20px;
  /*arriba/abajo - laterales*/
  padding: 20px 10px;
  /*Arriba - laterales - abajo*/
  padding: 20px 10px 5px;
  /*Arriba - derecha - abajo - izquierda*/
  padding: 20px 10px 5px 0px;
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

- A su vez las propiedades width-style-color, TAMBIEN SON SHORTHAND, que controlan cada uno del lado de los bordes, Top-Right-Bottom-Left
  ```css
  /*Algunos ejemplos*/
  border-top-style: Estilo de arriba;
  border-bottom-color: Color de abajo;
  border-left-color: Ancho de la izquierda;
  ```

## Valores de Border-Style

Listado de valores para style:

```css
.ejemplo {
  /* Quita los bordes */
  border-style: none;

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

- content-box => Valor por defecto
- border-box => Calculo de tamaño del elemento incluyendo el padding y el border

Es decir, si queremos que una caja mida un tamaño determinado, incluyendo el padding que pueda tener y el border, utilizamos "border-box", de lo contrario la caja medira cierto valor y sobre ese se le sumara el tamaño del padding y border.

## BUENA PRACTICA DE SELECTOR UNIVERSAL

Como casi siempre queremos que el navegador re calcule el tamaño por nosotros, utilizamos el SELECTOR UNIVERSAL para definir "box-sizing: border-box;"

```css
* {
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
.ejemplo {
  /* El primero sera para el eje X y el otro para el eje y */
  border-top-left-radius: 50px 100px;
}
```

Si lo que queremos es que todos los vertices de nuestra caja tengan la misma vertice, lo hacemos de la siguiente manera.

```css
/* Dibujara 4 elipses con 50 en el eje X y 100 en el eje Y*/
.ejemplo {
  border-radius: 50px / 100px;
  -webkit-border-radius: 50px / 100px;
  -moz-border-radius: 50px / 100px;
  -ms-border-radius: 50px / 100px;
  -o-border-radius: 50px / 100px;
}
```

Y si queremos hacer los elipses diferentes en cada vertice con una sola linea haremos esto (Al principio es complicado pero es posible)

```css
.ejemplo {
  /* Asi haremos en cada vertice diferentes elipses, la primer elipse corresponde al PRIMER VALOR en el eje X con el PRIMER VALOR DESPUES DE "/" en en eje Y y asi respectivamente  */

  /* A la izquierda los radios en el eje X y a la derecha los radios en el eje Y */

  border-radius: 100px 200px 300px 400px / 400px 300px 200px 100px;
}
```

- NOTA: Existe una propiedad mas para "Border-Radius" llamada "Border-Image" PERO aún no la veremos

# 18. OverFlow

_Decimos que un contenido se desborda, cuando la caja es mas pequeña que el contenido_

Overflow es la propiedad que utlizamos para contener el desbordamiento de las cajas, controlamos el desbordamiento del contenido, tenemos 4 valores para OverFlow:

- visible (valor por defecto, seguiria igual)
- hidden (Se esconde el desborde)
- Scroll (Aparece la barra para hacer Scroll)
- Auto (El mas recomendado Aparece la barra de Scroll SOLO SI HACE FALTA)

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

- Este es un problema que no tiene solución, entonces la recomendación es ir empujando los elementos hacia abajo (No juntar margin-bottom con margin-top, porque sera un dolor de cabeza)

- Solo sucede con los margenes verticales, los horizontales NO SE UNEN y se separan CORRECTAMENTE

## Problema 2 - Margen entre padres e hijos

Cuando un hijo tiene un margen y por defecto arrastra al padre (Lo descuadra)- NO TIENE SOLUCIÖN peor hay truco para arreglarlo

```css
/* El elemento padre debera tener alguna de estas 3 opciones */
.ejemplo {
  overflow: hidden;
  padding-top: 0.1px;
  border-top: 0.1px solid #color;
}
```

Con alguna de estas 3 opciones evitamos que el margen del hijo arrastre al elemento del padre

# 20. Display

Nos sirve para cambiar el contexto dentro del navegador, es decir si tenemos elementos de bloque o elementos de linea, podemos modificar su comportamiento con display

Admite varios valores:

- none => Hace que el elemento no se muestre, pero siga cargandose (Lo esconde a la vista, pero ocupa espacio)

- block => Hace que el elemento sea de bloque (Se convierte en un elemento de bloque)

- inline => Hace que el elemento sea de linea (Lo convierte en un elemento de linea)

- inline-block => Hace que el elemento sea de linea pero admite medidas y margenes verticales (El elemento sera de linea PERO ahora podemos colocarle Margenes y medidas como un elemento de BLOQUE)

- HAY MAS PERO NO LAS VAMOS A VER AÚN

# 21. Outline

Outline es la propiedad que nos permite dibujar un borde FUERA del modelo de caja

- Es un shorthand que indica width, style, color, exactamente como border, asi como la sintaxis

DIFERENCIAS EN COMPARACION A BORDER

- No ocupa sitio ya que no forma parte del box-model (No empuja las demas cajas del alrededor NO ESTORBA LAS DEMAS CAJAS)
- No se puede redondear (Porque no pertenece al box-model)
- No se pueden controlar los lados de forma independiente

Tambien cuenta con la propiedad "outline-offset", que nos permite aumentar o disminuir la DISTANCIA del outline respecto a la caja a la que pertenece

```css
.outline {
  /* Es un shorthand identico en sintaxis a border */
  outline: 3px inset lightcoral;
  /* Para que el outline este dentro de la caja */
  outline-offset: -13px;
}
```

# 22. Text Align

Es la propiedad que nos permite alinear HORIZONTALMENTE el contenido de un ELEMENTO DE BLOQUE siempre que el contenido **NO TENGA ANCHO DECLARADO**.

Acepta 4 posibles valores:

```css
.selector {
  /* Por defecto */
  text-align: left;

  text-align: right;
  text-align: center;

  /* justify no es recomendable, porque genera espacios no proporcionales para FORZAR LA JUSTIFICACIÓN */
  text-align: justify;
}
```

## Elementos de BLOQUE

"text-align" centra el **contenido(Lo que esta dentro)** NO el **contenedor(La caja)** al que le demos la propiedad.

Si deseamos centrar el CONTENEDOR desde el mismo utilizamos el "truco de MARGIN:AUTO"

```css
.box {
  /* Centramos el CONTENIDO dentro de la CAJA */
  text-align: center;

  /* Centramos el CONTENEDOR (CAJA) */
  margin-left: auto;
  margin-right: auto;
}
```

## ELEMENTOS DE LINEA

En los elementos de linea el contenido no se va a centrar NUNCA puesto que es un elemento de linea, si queremos centrarlo, convertirelos el elemento en BLOQUE con "display:block"

```css
.link {
  /* Asi se debe hacer si queremos centrar un elemento de linea */
  display: block;
  text-align: center;

  /* NO SE PUEDE CON "inline-block" solo con "block" */
}
```

## IMAGENES

"text-align" NO SIRVE en imagenes si uno quiere centrar directamente la imagen, porque el bloque es la misma imagen, entonces para centrar "img" usamos el "truco MARGIN"

Si lo que queremos es centrar la imagen dentro de un contenedor externo (div) SI ES POSIBLE CON "text-align:center"

```css
.img {
  /* NO FUNCIONA ASI */
  display: block;
  text-align: center;

  /* Esta es la forma si queremos centrar DIRECTAMENTE DESDE EL ELEMENTO IMG */
  margin-left: auto;
  margin-right: auto;
}

.img-container {
  /* En este caso como es un contenedor externo SI FUNCIONA "text-align:center" - siempre y cuando la imagen no sea "display:block" */
  text-align: center;
}
```

**NOTA: Cuando vayamos a centrar, tengamos en cuenta SIEMPRE si lo que queremos centrar es el CONTENIDO de una caja o la CAJA en si (Esto nos va a ayudar a saber que usar)**

# 23. Box-shadow

Se creo para añadir efectos de sombra a nuestra caja.

En esencia lo que hace es crear un clon de la caja respetando la forma de su box-model (ancho, alto, redondez)

La sintaxis de esta propiedad es distinta, en función a lo que queramos conseguir.

- offset-x => Desplazamiento en el eje x OBLIGATORIO
- offset-y => Desplazamiento en el eje y OBLIGATORIO
- blur-radius => Desenfoque de la sombra
- spread-radius => Expansión de la sombra
- color => El color de la sombra (si no lo especificamos, lo heredara del elemento al que pertenece)
- inset => Determina si la sombra sera interior o exterior

"box-shadow" puede tener todas las sombras que quiera, dentro del mismo atributo solo se separan con ","

```css
.box {
  /* Eje x | Eje y */
  box-shadow: 10px 200px;

  /* Eje x | Eje y | Blur-radius(desenfoque) */
  box-shadow: 10px 200px 10px;

  /* Eje x | Eje y | Blur-radius(desenfoque) | Spread-radius(Expansión) */
  box-shadow: 10px 200px 10px 20px;

  /* Eje x | Eje y | Blur-radius(desenfoque) | Spread-radius(Expansión) | color */
  box-shadow: 10px 200px 10px 20px red;

  /* El valor inset para que la sombra se dibuje por dentro (parece que fuera relieve) */
  box-shadow: inset 10px 200px 10px 20px red;

  /* Para crear mas de una sombra las separamos con , */
  box-shadow: 10px 10px red, 5px 5px blue, 3px 3px green;
}
```

**NOTA: Funciona como outline, NO ocupa sitio del "box-model"**

# 24. Position

La propiedad position nos permite posicionar los elementos.

## Conceptos IMPORTANTES para entender "Position"

Hay algunos conceptos que debemos conocer para entender "position"

- Flujo de renderizado => Por norma general TODOS LOS ELEMENTOS se van a dibujar de IZQUIERDA A DERECHA y de ARRIBA A ABAJO. Lo que hace que el punto 0,0 de todos los elementos sea la esquina superios IZQUIERDA.

- Espacio reservado => Es el espacio que tiene un elemento asignado en el navegador, para que ningún otro elemento entre dentro de ese espacio

- Elemento posicionado => Esto significa que el elemento tiene la propiedad "position" con un valor diferente de "static", que es el valor por defecto

- Stackin context => Contexto de apilamiento. Es el orden en el que se apilaran las cajas que se superponen, dentro del mismo contenedor

## Uso

Al posicionar un elemento se habilitan 5 propiedades que podemos utilizar para mover los elementos en los 3 ejes.

- top => El elemento se movera desde la parte superior, la distancia que le hayamos indicado.

- right => El elemento se moverá desde la parte derecha la distancia que le hayamos indicado

- bottom => El elemento se movera desde la parte inferior, la distancia que le hayamos indicado

- left => El elemeto se movera desde la parte izquierda la distancia que le hayamos indicado

- z-index => Nos permite mover el elemento en el contexto de apilamiento (eje Z)

**NOTA: Si un elemento le declaramos la propiedad top y/o left, la propiedades bottom y/o right no funcionaran (Siempre le hara caso a top y a left, por encima de bottom y right)**

## Valores de Position

Los posibles valores que le podemos dar a position son.

- Static => Es el valor que tiene por defecto un elemento, con este valor el elemento NO ESTA POSICIONADO y por lo cual no podremos moverlo

- Relative => El elemento mantendra su posición y medidas en el flujo de renderzado, y mantendra su espacio reservado. Si lo movemos lo hará usando su posición en el HTML como punto de referencia.

- Absolute => El elemento perdera sus medidas y su espacio reservado. Si lo movemos usará el elemento padre posicionado como referencia. Si no tiene ninguno, usará el elemento html de referencia

- Fixed => El elemento perdera sus medidas y su espacio reservado. Si lo movemos usará el elemento html de referencia, y ademas se quedará fijo en esa posición aunque hagamos scroll

- Sticky => Es una mezcla de position relative y fixed. Con este tipo de posicionamiento los valores (Top, left, right, bottom) NO sirven para mover el elemento, sino para indicarle en que punto pasará a tener un comportamiento de posicionamiento "fixed", hasta llegar a ese punto se comportará como si tuviera "relative"

# 25. Position Relative

El elemento mantendra su posición y medidas en el flujo de renderzado, y mantendra su espacio reservado. Si lo movemos lo hará usando su posición en el HTML como punto de referencia.

```css
.box-1 {
  background-color: lightcoral;

  /* Se movera 100px de izquierda a derecha, desde su punto inicial de referencia que seria (la esquina superior izquierda)*/

  /* Su espacio sigue quedando reservado, por lo que  ningún objeto lo busca ocupar a pesar que este se haya movido*/
  position: relative;
  left: 100px;
}
```

- Otra cosa que podemos hacer con la propiedad "position" es obligar a los elementos a ocupar un mismo espacio, las cajas que esten mas abajo en el HTML seran las que se SUPERPONEN en el orden (Es decir las que estan "adelante" y se "ven" en caso de que ambas ocupen un mismo espacio)

  - **NOTA: En esas ocasiones es donde se maneja el concepto de apilamiento**

- ## Top y left priorizan sobre bottom y right

  ```css
  .box-2 {
    background-color: lightgreen;
    position: relative;

    /* Mientras sean invocadas las sentencias top y left, siempre seran prioridad, por lo que bottom y right no funcionaran mientras top y left existan */
    top: 50px;
    left: 50px;

    bottom: 100px;
    right: 100px;
  }
  ```

- ## Las sentencias reciben valores tanto Positivos como Negativos

  ```css
  .box-2 {
    background-color: lightgreen;
    position: relative;

    /*Los valores negativos tambien se aceptan, lo que quiere decir que estos 2 valores hacen lo mismo*/
    top: 100px;
    bottom: -100px;
    /*Cualquiera de los 2 bajara el elemento 100px (Da exacamente igual)*/

    /*En un futuro con "mediaQuery" y otras cosas, hay que tener mas en cuenta que conviene mas, para que no se sobreescriba y sabremos si usar valores negativos o positivos*/
  }
  ```

- Los elementos que no son cuadrados (EJ:Un circulo), los elementos se comportan igual, porque CSS, usa CAJAS aunque no se vean, por lo tanto todo tiene esquinas

# 26. Position Absolute

El elemento perdera sus medidas y su espacio reservado. Si lo movemos usará el elemento padre posicionado como referencia. Si no tiene ninguno, usará el elemento html de referencia

## Sin contenedor padre

```html
<body>
  <!-- No tiene contenedor padre, entonces usa de referencia el HTML -->
  <div class="box-1"></div>
  <div class="box-2"></div>
</body>
```

```css
.box-2 {
  background-color: lightgreen;
  /* Perdera las medidas por defecto, pero si se le pueden declarar medidas (Eso entendí) */
  position: absolute;
  bottom: 0;
  /* Se posicionara respecto al contenedor padre, sino tiene respecto a todo el HTML */
}
```

- Cuando colocamos un "position:absolute" a un elemento, pierde su espacio de renderizado, por lo que para el codigo ahí ya no hay nada y lo que hace es ocupar ese espacio con otro elemento.

## Con un contenedor padre

- Para que un elemento con un contenedor padre, se ubique en referencia a este, el contenedor padre DEBE ESTAR POSICIONADO, no importa que tipo de posicionamiento sea, el elemento lo tomara de referencia siempre y cuando este posicionado (NO HACE FALTA QUE EL ELEMENTO SEA HIJO DIRECTO)

```html
<body>
  <div class="cotainer">
    <!-- La caja 1 tiene padre -->
    <div class="box-1"></div>
  </div>
  <!-- La caja 2 NO tiene (se ubica respecto al HTML) -->
  <div class="box-2"></div>
</body>
```

```css
/* Para que el elemento padre funcione DEBE estar POSICIONADO */
.container {
  position: relative;
}

/* Este elemento se ubica respecto al elemento padre que es .container (No tiene porque ser hijo directo para que funcione) */
.box-1 {
  background-color: red;
  position: absolute;
  left: 100px;
}

/* Este elemento se ubica respecto al HTML porque no tiene elemento padre */
.box-2 {
  background-color: lightgreen;
  position: absolute;
  left: 100px;
}
```

## Truco de "position:absolute"

- Cuando nosotros posicionamos un elemento de linea, automaticamente le estamos dando el contexto de bloque para darle medidas (Entonces no hace falta el "display:block" para que nos lea el width y el height)

```css
.link {
  /*Es un elemento de linea, pero como tiene posiition:absolute, da el contexto de bloque, asi que nos aceptara width y height y las propiedades de bloque*/
  position: absolute;
  width: 100px;
  height: 100px;
}
```

# 27. Position Fixed

El elemento perdera sus medidas y su espacio reservado. Si lo movemos usará el elemento html de referencia, y ademas se quedará fijo en esa posición aunque hagamos scroll

- El elemento de referencia de fixed SIEMPRE sera el HTML, da igual que este entre otros contenedores

- la gracia de position fixed, es que el elemento no se va a mover de ahí, como un "header" fijo

```css
/* Asi tenemos nuestro header fijo y no se pierde */
.header {
  text-align: center;
  padding-top: 25px;
  background-color: lightskyblue;
  color: orange;
  position: fixed;
  top: 0;
  width: 100%;
}
```

**NOTA: Todo lo que vimos de "pos:absolute" es exactamente igual aca salvo que este siempre es respecto al HTML SIEMPRE y que este se mantiene asi se haga scroll, de resto es lo mismo**

# 28. Position Sticky

Es una mezcla de position relative y "fixed" (aunque no es exactamente fixed).

Con este tipo de posicionamiento los valores (Top, left, right, bottom) NO sirven para mover el elemento, sino para indicarle en que punto pasará a tener un comportamiento de posicionamiento similar al que tiene "fixed", hasta llegar a ese punto se comportará como si tuviera "relative"

- Lo que realmente hace "stycky" es fijar el elemento como "fixed" PERO durante el largo del elemento padre (Si yo tengo una SECCION con un H2, el h2 se comportara como fixed unicamente lo que dure la seccion, cuando esta acabe, el h2 volvera a su posicion)

```css
/* La seccion mide 200px */
section {
  height: 200px;
}

h2 {
  /* sticky va a mantener el titulo pegado arriba del todo (porque le colocamos "top:0" durante el alto de su padre (section) que es de 200px, despues dejara de desplazarse con el scroll*/
  position: sticky;
  top: 0;
  /*Lo que agarra como referencia siempre es el alto del elemento padre*/
}
```

- STICKY NO FUNCIONA SI:

  - El elemento padre no tiene un alto, o el alto no es suficiente para que el elemento se pegue.

  - El elemento padre tienen un "overflow" DIFERENTE a "visible", si tiene "hidden" o cualquier otro valor NO se pegara el elemento

# 29. Propiedad Z-Index

Es la propiedad que nos permite ordenar los elementos superpuestos para controlar cual se coloca delante y cual por detras

**NOTA: Si 2 elementos estan posicionados (Sin ningún "Z-Index") el valor que vale es el del HTML, se superpone el que este de ultimas en el HTML**

## Uso

- Lo necesario para usar z-index es que si o si el elemento DEBE estar POSICIONADO

- El valor por defecto de z-index es "auto", (calcula automaticamente cual es su contexto de apilamiento)

- El numero mayor es el que prevalece, un "z.index: 10" se va a poner por delante que un "z-index: 5"

```css
.box-1 {
  background-color: lightgreen;
  position: relative;

  /* Este va a arriba, porque a pesar de estar antes en el HTML, le estamos cambiando su contexto de apilamiento con z-index */
  z-index: 1;
}

/* Por defecto este deberia estar arriba del "box-1" porque va de ultimas en el HTML y ambas cajas estan posicionadas, pero no va arriba porque estamos modificando el contexto de apilamiento a la otra caja con "z-Index" */
.box-2 {
  background-color: lightseagreen;
  position: relative;
}
```

## Normas a tener en cuenta

- NO utilizar numeros consecutivos, EJ= "z-index:1" , "z-index:2" (Porque tarde o temprano toca añadir mas elementos), mejor utilizarlo de 10 en 10 o de 100 en 100

- El Contenedor(elemento) padre JAMAS se va a colocar por delante del hijo, por mas z-index que tenga. LO QUE SI SE PUEDE HACER, es que el HIJO se coloque DETRAS DEL PADRE

  - Esto se logra dandole un "z-index" al hijo con un valor NEGATIVO y que el padre NO tenga un "z-index" DECLARADO (si lo tiene declarado NO va a funcionar)

# 30. Stacking Context

Es el algoritmo que usa el navegador, para colocar las cajas que nosotros vayamos apilando (En que orden).

Es el espacio donde nuestros elementos se van a ir apilando para que unos queden por detras de otros.

- Las cajas se superponen a las cajas PERO NO al contenido que estas tengan, las cajas pueden tener contextos de apilamientos diferentes (Es algo confuso)

- Existen propiedades que generan contextos de apilamiento distintos, por lo que puede que muchas veces asi queramos el z-index no funciona bien (Es algo confuso)

## El orden del stacking context es: (de adelante a atras):

Por lo general este es el orden que se va a seguir:

- Elementos posicionados con un z-index de 1 o mas

- Elementos posicionados sin un z-index declarado(z-index:auto)

- Elementos no posicionados

- Elementos con z-index negativo

**NOTA: Si solo depende del HTML, los elementos que se pongan por encima seran los que esten mas abajo, porque se renderizan despues**

# 31. Ordenar propiedades

Ordenar las propiedades es importante, no existe ninguna norma ni especificación sobre como hacerlo, pero la mayoria de los expertos coinciden en los mismos puntos

_La 1 y la 2 son intercambiables_

1. Propiedades de posicionamiento
2. Propiedades del box model
3. Propiedades de texto
4. Propiedades visuales (colores, bordes, BGC...)
5. El resto

EJEMPLO

```css
.ejemplo {
  position: relative;
  left: 100;
  top: 100;

  display: block;
  width: 100px;
  height: 80px;
  padding: 10px;

  text-align: center;
  font-family: "Courier New", Courier, monospace;
  font-size: 10px;
  font-weight: 600;

  border: 1px solid blue;
  color: red;
  border-radius: 1px;
  -webkit-border-radius: 1px;
  -moz-border-radius: 1px;
  -ms-border-radius: 1px;
  -o-border-radius: 1px;

  /*Varios*/
  opacity: 1;
  /* transform, transition, etc... */
}
```

**NOTA: El orden es irrelevante, pero es mejor ordenarlo asi**

# 32. Medidas Absolutas y relativas

Las podemos dividir en 2 grupos.

## Medidas Absolutas

Las medidas absolutas NO CAMBIAN y siempre mantendran su tamaño independientemente del dispositivo o la interacción al usuario

La mas usada es px(pixeles) cuya medida es 1/96 de 1in, pero existen mas como:

```css
.medidas {
  /* Centimetros */
  height: 100cm;
  /* Milimetros */
  height: 100mm;
  /* Cuarto de milimetro */
  height: 100Q;
  /* Inches, pulgadas */
  height: 100in;
  /* Picas */
  height: 100pc;
  /* Puntos */
  height: 100pt;
}
```

## Medidas Relativas

Las medidas relativas SIEMPRE dependen de un contexto, son las que se recomienda utilizar en la gran mayoria de ocasiones, porque nos van a permitir que todos los elementos se escalen proporcionalmente

Las mas usadas son **em, rem, %, vw, vh, vmin y vmax** aunque tenemos otras como:

- ex => Altura x de la fuente del elemento
- ch => La medida del ancho del glifo "0" de la letra del elemento
- lh => Altura de la linea del elemento

# 33. Medida EM y REM

- El estandar del tamaño de fuente por defecto en la raiz del documento es de 16px, y NO ES RECOMENDABLE MODIFICARLO

**NOTA: Tanto "em" como "rem" se calcula en base a la propiedad font-size (tamaño de fuente)**

## REM

Corresponde a la medida de la "m" de la raiz del documento HTML.

ejemplo: 16px = 1 rem

## EM

Corresponde a la medida de la "m" del contexto donde nos encontremos

Ejemplo: si el contexto es una caja con un font-size de 10px. El "em" seria

- 2em = 20px
- 1em = 10px

porque "em" es relativo al CONTEXTO donde este y NO a la raiz

## RECOMENDACIÓN

### Cuando usar REM

- Para tamaños de FUENTE hay que utilizar SIEMPRE "rem".
- Si la medida debe ser proporcional al tamaño de fuente de la raiz utilizar "rem"

### Cuando usar EM

- Cuando le damos un padding a un boton o elemento, y queremos que se mantenga su "aire" independiente de la fuente que le pongamos, utilizamos "EM"

- Si la medida debe ser proporcionalmente al tamaño del texto del elemento, utilizar "EM"

```css
.link {
  background-color: lightcoral;
  color: #333;
  /* La colocamos en EM porque debe ser proporcional al tamaño de texto de boton (para que tenga mismo "aire") */
  padding: 1em 2em;

  /* La colocamos en REM porque es una fuente y debe ser proporcional al tamaño de fuente de la raiz "html" */
  font-size: 2rem;
}
```

# 34. Width en % y Width Auto

## % (Porcentaje)

Cuando usamos porcentaje usamos de referencia el tamaño del contenedor y el navegador calcula ese porcentaje. Esto no ocurre cuando usamos transform.

**NOTA: Si queremos que un elemento se ajuste al tamaño de su ventana es MUY COMODO utilizar porcentajes**

- El problema de los porcentajes viene cuando lo tenemos declarado y adicional le queremos dar un margen, porque lo que hara es dejar del mismo tamaño el elemento y agregara las MARGENES, lo que ocasiona un desbordamiento, eso lo podemos arreglar usando en vez de porcentajes, el valor AUTO

## Auto

Cuando usamos auto le pedimos al navegador que calcule en función del espacio disponible, lo que hace auto es calcular el espacio que tengo y abarcarlo, si tengo margenes y eso, lo descuenta y abarca el 100% teniendo en cuenta las margenes y otros valores

```css
.box-children {
  /* Respecto a la caja, si lo dejara asi tendria el tamaño de la caja padre + las margenes (SE DESBORDADIA) */
  width: 100%;
  margin: 0 50px;
  /* Aca ocupa 100% + 50px */

  /* La forma CORRECTA es con AUTO, con auto, las margenes y el contenido no ocuparian mas del 100% de la caja padre */
  width: auto;
  margin: 0 50px;
  /* Aca ocupa 100% en total */
}
```

# 35. Height en % y Height Auto

## %(Porcentaje)

Cuando estamos dentro de un contenedor, este tiene que tener un alto declarado, si no no podra calcular el porcentaje. Si se le aplica una medida con porcentaje se sustituira automaticamente por "auto"

## Auto

Cuando utilizamos auto el alto lo calculará el navegador en base al contenido del elemento

**NOTA: Height es una propiedad que tienes que usar con mucho cuidado. Si no es necesario establecer un alto, deja que el contenido sea el que decida el alto del elemento**

```css
.container {
  /* Para que el porcentaje de box 1 funcione, el contenedor debe tener un alto declarado (De lo contrario el height de box sera "auto") */
  height: 300px;
}

.box {
  /* Este funcionara siempre y cuando su contenedor tenga un alto declarado, de lo contrario el valor sera "height:auto;" */
  height: 50%;

  /* Se medira en base al contenido que tenga, si esta vacio, el contenido sera 0 y su alto igual */
  height: auto;
}
```

- Si nosotros usamos height:100% en una caja cuyo padre sea el body, la caja NO OCUPARA TODO, unicamente el valor pasara a ser "auto" y ocupara lo de su contenido, porque body no tiene NUNCA un alto declarado

```css
/* Esta caja tiene como padre al body */
.box {
  /* Ocupara unicamente lo que ocupe su contenido, porque body no tiene height declarado, entonces seria lo mismo que tener un height:auto */
  height: 100%;
}
```

**MUCHO CUIDADO AL USAR HEIGHT**

## Problema con height y el posicionamiento

- Cuando nosotros utilizamos "position:absolute/fixed", el height deja de correspoder al contenedor y se empieza a calcular respecto al "viewport" (VIEWPORT equivale a todo el espacio visible que tenemos en el navegador)

- Con "position: relative/sticky" no pasa esto.

```css
.box {
  position: absolute;
  /* Este 50% Correspondera al 50% del VIEWPORT y no de la caja contenedora */
  height: 50%;
}
```

# 36. Unidades de Viewport

## VIEWPORT

El viewport es el area util en donde se mostrara la pagina web. IMPORTANTE, toca tener en cuenta que es el area visible SIN HACER scroll.

Podemos usar el viewport como medida de varias formas:

- vw => **viewport Width**: hace referencia al ancho del viewport.

- vh => **viewport Height**: hace referencia al alto del viewport.

- vMax => Utiliza el valor mas grande entre el ancho y el alto del viewport.

- vMin => Utiliza el valor mas pequeño entre el ancho y alto del viewport.

  - 1vw = 1% del ancho del viewport
  - 1vh = 1% del alto del viewport
  - 1vmin = 1% del valor que sea mas pequeño del viewport
  - 1vmax = 1% del valor que sea mas grande del viewport

EJ - viewport height:

```css
.header {
  /* Se ajusta al alto de la ventana (Es completamente relativa al tamaño del navegador), una vez se de scroll empezara a aparecer el resto de contenido */
  height: 100vh;
}
```

EJ- viewport width:

```css
.header {
  /* Cuando utilizamos 100vw, no tenemos en cuenta la barra de scroll de los navegadores, por lo que se desborda y hay un scroll horizontal (En moviles no hay barra por lo cual esto no da problemas) */
  width: 100vw;

  /* En los casos en los que tengamos un hijo del body, no utilicemos 100vw, es mejor utilizar 100% (En caso de necesitarlo) para no tener problemas */
  width: 100%;
}
```

- Dependiendo de lo que queramos conseguir, nos interesa usar porcentaje o medidas de viewport, (El viewport SIEMPRE es respecto al tamaño de la ventana) (El % SIEMPRE es respecto al tamaño del contenedor)

## Viewport Min y Max

Es una medida siempre relativa al ancho y alto del Viewport, NO es un valor que se utilice en muchos sitios, pero si va a ser necesarios para algunas ocasiones en los que nos ayudaran con las FUENTES u OTRAS COSAS

- Si tengo MIN y la pantalla es vertical AGARRA El VALOR DEL ANCHO, si la pantalla es horizontal AGARRA EL VALOR DEL ALTO, (Siempre el valor mas pequeño)

- Si lo tengo en MAX pasara al reves, agarrara el valor mas grande

# 37. MIN/MAX Width y height

Son limitadores de Ancho y de Alto.

cuando establecemos un width y/o height con una medida que es relativa, es posible que no queramos que se respete esa medida en todos los casos.

Para ello tenemos propiedades que limitan esas medidas:

- min-width: Indica el ancho minimo que puede alcanzar el elemento

- max-width: Indica el ancho maximo que puede alcanzar el elemento

- min-height: Indica el alto minimo que puede alcanzar el elemento

- max-height: Indica el alto maximo que puede alcanzar el elemento

```css
.box {
  /* El elemento crecera y disminuira con la caja */
  width: 100%;

  /* Pero cuando llegue a 600px, dejara de crecer y cuando llegue a 300px dejara de achicarse (Establecemos limites) */
  max-width: 600px;
  min-width: 300px;
  /* Las medidas de height (No se utilizan demasiado), pero esta bueno conocerlas */
}
```

## Truco de min-height

Para cuando queramos que un elemento (como un footer) siempre se quede abajo, aunque el contenido NO RELLENE, utilizamos min-height.

```css
/* Para pegar un footer abajo asi el contenido no ocupe todo el viewport, podemos posicionar el footer abajo, (respecto al body), y tambien darle al body un TAMAÑO MINIMO */

body {
  /* Para que el footer se ubique respecto a el debe estar posicionado */
  position: relative;
  /* Para que lo minimo que mida sea lo de la pantalla */
  min-height: 100vh;
}

.footer {
  /* Para que se ubique siempre abajo del body sin importar el contenido */
  position: absolute;
  bottom: 0;
}
```

# 38. Colores en CSS

La mayoria de las pantallas funcionan con un modo de color aditivo. La suma de RGB da como reultado el blanco. Tenemos varias formas de dar color en CSS

## BGC(Background-color) VS Color

- BGC: Hace referencia al color de la caja
- Color: Hace referencia al color del contenido (texto y eso)

## Las keywords(palabras clave)

Son colores basicos y extendidos que ya vienen definidos por la W3C

En un desarrollo real no es común utilizar este tipo de colores por que no pueden perzonalizarse a gusto

**IMPORTANTE: Recuerda que existe el color "transparent"**

- Transparent es muy util en muchos trucos de CSS, sobremtodo cuando queremos hacer algunas figuras geometricas

EJEMPLO CON TRANSPARENT.

```css
/* Si queremos realizar un triangulo que apunte a diferentes direcciones, lo podemos hacer con los bordes de una caja y con transparent */

.box {
  /* Va a ser un triandulo que apute hacia arriba */
  border-bottom: 500px solid red;
  /* Le colocamos bordes a sus 2 laterales (left y right) y seran transparent para que no se vean */
  border-left: 250px solid transparent;
  border-right: 250px solid transparent;
}
```

# 39. CurrentColor

Es una palabra clave que se puede usar en lugar de cualquier valor de color, y usara el valor ya sea establecido o heredado en la propiedad color.

EN MIS PALABRAS

Current color es un valor que se le puede asignar a todas las propiedades que acepten color, y que va a equivaler al valor "color" mas cercano, no importa si es padre,abuelo, etc...**Es una especie de variable de color**

- inherit NO es lo mismo, porque hereda el color de LA PROPIEDAD no del color

  ```css
  .padre {
    color: red;
    background-color: blue;
  }

  .hijo {
    /*El color es "blue", porque heredo el color de la propiedad con inherit*/
    background-color: inherit;

    /*Aca el color es red, porque hereda de la propiedad COLOR del padre*/
    background-color: currentColor;
  }
  ```

  **CurrentColor ya no es tan usado por las propiedades CSS que veremos en el otro curso, pero es importante tenerlo en cuenta por si algun dia nos llega a hacer falta**

```css
.abuelo {
  /* Este valor no es el que se hereda con currentColor */
  background-color: red;

  /* Este si */
  color: blue;
}
.padre {
  /* El bgc sera de color azul, porque hereda la propiedad COLOR del padre*/
  background-color: currentColor;
}
.hijo {
  /* El color sera azul porque hereda la propiedad color del ABUELO */
  color: currentColor;
}

.hijo2 {
  color: green;
  /* Aqui el color del borde sera "green" porque agarra el color mas cercano que es el que el mismo asigno */
  border: 1px solid currentColor;
}
```

**Si NO hay ninguna propiedad que defina color, va agarrar la de por defecto del navegador, que normalmente es NEGRO**

# 40. Colores RGB y RGBA

En el modo RGB tenemos tres canales (Red, Blue, Green) y tenemos 8 bits de color por canal, (cada bit tiene dos posibles valores 0 ó 1) Lo que significa que tenemos 2^8 posibles valores, que van desde 0 hasta 255.

- Esto da un total de 255* 255 * 255 = 16.581.375 colores.

- Su sintaxis es rgb (R,G,B)

- Si ponemos todos los canales de 0 tendremos un negro puro y si los ponemos a 255 tendremos un blanco,

- Para movernos por la gama de grises debemos poner los 3 canales con el mismo valor (Cuanto mas cercano estemos a 0 será un gris mas OSCURO y viceversa). Si todos los canales estan en 128 tendremos un gris puro.

## Canal Alpha RBGA

El modo RGB nos da la opción de utilizar un CUARTO CANAL que corresponderia al CANAL ALPHA, es decir, la TRANSPARENCIA, y su valor va de 0 a 1. Tenemos dos sintaxis para utilizar el CANAL ALPHA:

- rgba(R,G,B,A)
- rgb(RGB / A)

```css
/* RGB Normal */
.box {
  background-color: rgb(255, 255, 0);
  color: rgb(0, 255, 170);
}

/* RGBA - Con Alpha (2 Sintaxis) */
.box {
  background-color: rgba(255, 255, 0, 0.5);
  color: rgb(255 255 255 / 0.3);
}
```

# 41. Color Hexadecimal

**Es como el RGB pero codificado de otra forma**

La notacion hexadecimal es la mas común en desarrollo web, se basa en los mismos principios que el RGB pero escrito en notacion hexadecimal.

El sistema hexadecimal es un sistema basado en 16 valores del 0 al 15. Utiliza los digitos del 0 al 9 y las letras de la A a la F

En este tipo de notación también necesitamos 256 valores. Se compone de 16 caracteres en parejas, ya que 16\*16= 256

- 0 1 2 3 4 5 6 7 8 9 A B C D E F
- 0 1 2 3 4 5 6 7 8 9 A B C D E F

Para indicar que vamos a utilizar la notacion hexadecimal, utilizamos el simbolo de numero "#" y a continuación isaremos esta notacion por parejas.

- #RRGGBB -> Cuando una pareja usa el mismo valor se puede omitir el segundo valor, siempre y cuando se haga en las 3 parejas

  - EJEMPLOS

    - El color NEGRO es #000000 porque es el valor minimo del hexadecimal, pero lo podemos modulizar asi #000 (Cada 0 representa una pareja)

    - El color BLANCO es #ffffff porque es el valor maximo del hexadecimal, pero lo podemos modulizar asi #fff (Cada F representa una pareja)

    - El color ROJO es #ff0000 Porque es el valor maximo en el canal RED y el minimo en los otros canales, pero lo podemos modulizar porque las parejas tienen valores iguales y queda asi #f00

## Transparencia con Hexadecimal

Aqui tambien tenemos la opcion de añadir un CUARTO CANAL

- Lo unico que tenemos que hacer es agregarle otra pareja al hexadecimal, o si usamos el metodo abreviado, otro numero que represente el cuarto canal

```css
.box {
  /* Transparencia de la forma normal (Se agrega la pareja del canal alpha) */
  color: #00000080;

  /* Transparencia con el metodo abreviado (Tambien tenemos que abreviar la transparencia) */
  background-color: #fff7;
}
```

# 42. Color HSL y HSLA

El modo de color HSL es el mas intuitivo para los humanos. Su nombre viene de las sigles Hue (tono), Saturation (Saturación) y Lightness (Luminancia).

- El primer valor es el ángulo en el circulo cromático donde 0 y 360 sera el color rojo. Hay ciertos valores que nos pueden servir como referencia para relacionar mejor los colores con sus angulos.

  - 0 => Rojo
  - 60 => Amarillo
  - 120 => Verde
  - 180 => Cyan
  - 240 => Azul
  - 300 => Magenta

- El segundo valor es la saturación o intensidad del color. 0% => gris || 100% => color puro

- El tercer valor es la luminosidad del color. 0% => Negro, nada de luz || 100% => Blanco, luz maxima

_"En web no se suele utilizar ni blanco puro, ni negro puro"_

**NOTA: Es importante que aunque el valor de saturacion o luminancia sea 0, hay que poner 0%, sino no funcionara**

```css
/* Se supone que con este tenemos un control practicamente absoluto (Me sigo quedando con RGB o hexadecimal) */
.box {
  /* Rojo puro */
  /* Angulo del croma, saturación, luminosidad */
  background-color: hsl(0, 100%, 50%);

  /* La sintaxis de transparencia funciona igual que en rgb */
  background: hsla(120, 100%, 50%, 0.7);
  background-color: hsl(120% 100% 50% / 0.5);
}
```

## Paginas para elegir colores, paletas Etc...

1. BrandColors (Nos dice la paleta de colores que utilizan las empresas)

2. htmlcolorcodes (Tiene una tabla de colores y si escogemos uno, nos sugiere una paleta de colores)

3. ColorHunt - Coolors (Nos da paletas completas que podemo elegir)

4. AdobeColor (Tenemos muchas opciones para elegir el color que nos guste, y hay muchas opciones)

## Modos de color Adicional

Existen otros cuatro modos de color en los que estan trabajando que serian:

1. CMYK (Cyan,Magenta,Yellow,Black)
2. HWB (Hue, Whiteness, Blackness)
3. lab (Lightness, distance a, distance b)
4. lch (lightness, chroma, hue)

Todos estan en el borrador del modulo de clor de nivel 4 pero aún no es estandar

# 43. Tipografia vs Fuentes

## Explicación de fuentes y tipografias

- La tipografia es la CIENCIA que estudia el DISEÑO y USO de los tipos de letra.

- Las fuentes son TIPOS ESPECIFICOS de letra.

- Los glifos son cada uno de los DIBUJOS que representan cada SIMBOLO de la fuente, incluidos espacios.

- Los estilos de fuente son las MODIFICACIONES que se hacen a la fuentes como el GROSOR o la INCLINACIÓN. (NO todas las fuentes tienen NEGRITA o CURSIVA - Lo que hace el navegador es FALSEAR esa "negrita")

- **Familia Tipografica** => son las diferentes fuenter que pertenecen a una misma BASE.
  - Arial, Arial black, Arial Narrow etc...

## Aplicación en CSS

- Cuando usamos la propiedad text-\* AFECTAMOS a un bloque completo (A mas elementos que solo la fuente)

- Cuando usamos la propiedad font-\* AFECTAMOS a la fuente del texto

## Fuentes Predeterminadas

Son las fuentes que se consideran **"seguras"** ya que son GENERICAS y NO establecen una familia tipografica, sino un estilo de fuente.

- Serif: Fuentes que tienen serifas (Adornos en los caracteres como "Times New Roman")

  - Si la vamos a usar, recomendado solo para titulos, NO para textos largos, porque suelen cansar mas los ojos

- Sans-Serif: Fuentes sin serifas (Como "Arial")

  - Son mas limpias y se recomiendan UTILIZARLAS para casi todo

- Monospace: Fuentes que tienen el mismo ESPACIADO entre todos sus caracteres.

  - Es como letra de maquina de escribir

- Cursive: Fuentes que pretenden emular escritura a mano, con ligaduras y trazos fluidos

  - Es como letra a "Mano"

- Fantasy: Fuentes que suelen ser decorativas
  - Es la que casi NUNCA se utiliza, pero ahí esta.

**Cuando utilizamos cualquiera de estas "fuentes" lo que hace realmente el navegador es AGARRAR alguna de las fuentes del Sistema operativo con la caracteristicas y UTILIZARLA**

- En windows agarra por defecto (En otros sistemas operativos puede que cambie):
  - sans-serif: arial
  - sefir: times new roman

# 44. Google Fonts

Las fuentes desde un SERVIDOR REMOTO son las fuentes que nosotros descargamos para poder UTLIZAR. El mas famoso de estos servidores es GOOGLE FONTS (Es gratuita)

SIEMPRE pero SIEMPRE, SIEMPRE, SIEMPRE que utilicemos fuentes NO genericas (Las que vimos anteriormente), TENEMOS que colocar fuentes genericas de fallback (RESPALDO)

## Que hay dentro de google fonts

Tenemos una lista de fuentes gigantesca, la podemos filtrar por:

- Categorias

  - Serif
  - Sans-Serif
  - Monospace
  - HandWriting(cursive)
  - Display.

- Lenguajes

- Font Properties
  - Numero de estilos de la fuente
  - Grosor de la fuente
  - Inclinación de la fuente
  - Ancho de la fuente

Cuando seleccionamos una fuente en especifico nos muestra:

- Nombre de la fuente y creador
- Opcion de descargar la familia de la fuente
- Todos los estilos de la fuente
- Glifos (Aca vemos si tiene tildes, numeros etc...)
- Licencia (En google todas son gratuitas, pero hay algunas con licencia especial)
- **IMPORTANTE:** Nos muestra las parejas POPULARES con la fuente que escogemos y como se ven juntas

## Como utilizar la fuente dentro de nuestra WEB

1. Elegimos el estilo de fuente que queremos (light, regular, bold, etc...) en "select this style"

2. Nos al menu de fuentes escogidas, donde nos apareceran todos los estilos que hemos escogido para IMPORTAR

3. Google da la opción de importar por "<\link>" o por "@Import".

   - Es recomendable NUNCA importarla por "@Import" y mucho menos desde un servidor remoto, porque si el servidor remoto falla, no cargarian los estilos que vayan despues de la linea "@import"

   - SIEMPRE utilicemos "<\link>"

4. Escogemos "link" y copiamos las etiquetas que nos muestran

   - Unas etiquetas son para conectarse a google font

   - La otra es directamente la de la fuente/fuentes que le indiquemos

5. La pegamos antes, SIEMPRE ANTES de nuestros estilos, para que no hayan errores

   - El "rel:preconnect" es para indicarle al navegador que nos conectaremos a un servidor remoto e inicie la carga LO ANTES POSIBLE.

6. Utilizamos nuestras fuentes en el CSS como nos indica GOOGLE FONTS para que no haya problemas

**NOTA: Entre mas fuentes importemos mas se demorarara nuestra pagina en CARGAR, lo habitual es traer una sola fuente o 2**

**EJEMPLO COMPLETO DE IMPORTAR FUENTES:**

HTML

```html
<head>
  <!-- Preconexion a google fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />

  <!-- Verificacion para que no haya problemas al importar fuentes -->
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />

  <!-- Link de TODAS las fuentes que deseamos importar(Es solo un link para todas las fuentes) -->
  <link
    href="https://fonts.googleapis.com/css2?family=Montserrat:wght@200;400;700&family=Roboto+Mono:ital,wght@0,100;1,100;1,200&display=swap"
    rel="stylesheet"
  />

  <!-- Estilos siempre por debajo para que no haya problemas -->
  <link rel="stylesheet" href="styles.css" />
</head>
```

CSS

```css
body {
  /* Cada fuente que usemos debe tener su fuente generica de respaldo por si falla la importación por algún motivo */
  font-family: "Montserrat", sans-serif;
  font-family: "Roboto Mono", monospace;

  /* Podemos colocar mas de 2 fuentes de respaldo, pero siempre debe existir una generica */
  font-family: "Montserrat", "Roboto Mono";
}
```
# 45. Google Icons

Es una libreria donde tenemos una gran cantidad de iconos que podemos utilizar en nuestra WEB.

## USO

1. Escogemos el icono que necesitemos.

2. Los podemos utilizar en Web, Android, IOS, Flutter.

3. Y podemos elegir, color, densidad(px) y el tamaño.

4. Importamos el link antes de nuestro CSS

   ```html
   <link
     href="https://fonts.googleapis.com/icon?family=Material+Icons"
     rel="stylesheet"
   />
   ```

   - Hay una duda aqui respecto si dependiendo el icono tenemos que importar otro link (NO LO SE)

5. Copiamos el "span" del icono que nos brinda google, y ya tenemos nuestro icono
   `<span class="material-icons-sharp"> info </span> `


   **NOTA: Si vas a usar una gran cantidad de iconos en tu web compensa usar la libreria remota.....Si sólo usaras unos pocos es mejor descargarlos en formato "svg" y utilizarlos como imagenes**

## Modificar Iconos de la libreria

  - Para modificar el tamaño del icono, lo podemos hacer con "font-size".

  - Para modificar el color, lo hacemos con la propiedad "Color".

## Modificar los Iconos desde SVG

Para modificar los iconos de SVG tenemos 2 opciones

1. Llamar al icono como imagen

    - Cuando el icono es llamado como imagen, podremos modificar el color unicamente desde el 'svg' con la propiedad 'fill'

2. Llamar al icono copiando el SVG (No es muy bueno hacerlo)

    - Cuando el icono se crea usando directamente la etiqueta SVG en HTML se le puede asignar una clase y modificar los estilos en CSS o directamente desde el codigo de ese SVG con la propiedad FILL

# 46. Font Face

  ## Existen diferentes formatos para fuentes
  - True Type Font (TTF) => Fue el primer formato estándar (Es el mas extendido y mas probable de encontrar)

  - Open True Type Font (OTF) => Facilita e implementa la creación de curvas. (Afecta mas que nada a los desarrolladores de fuentes)

  - Web Open Font Format (WOFF) (WOFF2) => Es un formato mucho más ligero y mejora el rendimiento. Funciona a traves de metadatos. WOFF Tiene soporte total y WOFF2 No funciona en internet explorer

  - Scalable Vector Graphics(SVG) => Para efectos y animaciones sobre el texto. NO ES RECOMENDABLE USARLO EN EL TEXTO GENERICO DE LA WEB, GENERA MUCHOS PROBLEMAS.

  - Embedded Open Type (EOT) => Primer formato digital propuesto para sitios WEB y es comprimido. Se quedo como una propuesta pero no pasó a ser un estandar

  ## Regla @font-face

  Esta es la forma de utilizar fuentes que tenemos descargadas y que no traemos de un servidor remoto, (Cuando usamos Google Fonts, esto es lo que esta pasando por detras)

  ## La sintaxis es: 
  ```css
      @font-face{
    font-family: pepe;
    /* (Nombre de la familia. se lo asignamos nosotros); */
    src:
    /* Aqui pondremos dos tipos de valores. */

        local()
         /* Pondremos el nombre de la fuente para buscarla en el ordenador del usuario, de esa forma podremos  */

        url()
        /* Si no encontramos esa fuente procederemos a descargarla. */


        /* Existe otro valor, menos usado que es format */
         format()
         /* Este valor lo pasaremos de forma opcional si queremos ser más especificos con la fuente que vamos a buscar o descargar, sino lo ponemos cogerá el primer formato soportado, si lo ponemos, y si no lo encuentra no hará nada */
  }
  ```
  A esta regla se le pueden añadir mas valores como: 
  - font-style

  - font-weight

  - font-display(experimental)
  
  Pero son completamente opcionales

## Paginas para descargar fuentes

  - 1001 Fonts
  - DaFont

  Hay algunas que son unicamente gratis para uso PERSONAL

## Uso de Font Face

 1. Descargamos la fuente de Internet 
 
 2. Creamos una carpeta 'fonts' en la carpeta 'assets' de nuestro proyecto.

 3. Pegamos la cuente en nuestra carpeta 'fonts'

 4. Utilizamos la regla font-face (La podemos colocar en cualquier lugar aunque normalmente se coloca ARRIBA)

 ```css
 @font-face{
    font-family: 'Mano Alzada';
    src: local("Great Vibes"), url(/assets/fonts/GreatVibes.ttf);
    /* En caso de que el usuario tenga esa fuente pues la usara, y sino descargara la que tenemos en el server */
  }
 ```
 ## Herramientas Utiles
 - Es posible convertir fuentes de un formato a otro con convertidores ONLINE

 - Extension de Chrome 'WhatFont' Para conocer las fuentes de una pagina web

 # 47. Decorar Textos

 ## Transformaciones de Texto 

**Text-transform:** Esta propiedad nos permite hacer transformaciones **ESTETICAS** en nuestro texto. Admite los valores:
    
  - none: No se aplicará ninguna trasformación

  - uppercase: El texto se pondra en Mayúscula

  - lowercase: El texto se pondra en Minusculas
    
  - Capitalize: Transforma la primera letra en Mayuscula.

El tema de que sea unicamente ESTETICO se refiere a que si lo intentamos recuperar desde otro lado (Como JavaScript) Lo recuperaremos tal cual fue escrito. **Esto es algo para tener muy en cuenta**

## Adornos en el texto

- **Text-Decoration:** Esta propiedad nos permite controlar la línea que podemos poner en los textos. Admite los valores:

  - none: Elimina cualquier linea.

  - underline: Coloca una linea bajo el texto.

  - overline: Coloca una linea sobre el texto.

  - line-through: Coloca una linea tachando el texto

- **Text-shadow:** Funciona exactamente como "box-shadow", con la UNICA DIFERENCIA de que no admite el valor inset, Ni la expansión de la sombra.Los valores son:

  - offsetX: desplazamiento Horizontal

  - offsetY: desplazamiento Vertical

  - blur: Desenfoque.

  - Color: color (por defecto coge el del texto)

  Tambien admite MULTIPLES SOMBRAS

# 48. Espaciado y orientación de TEXTO

- Letter-spacing:
Establece la separación entre caracteres, (se puede reestablecer en cualquier medida valida para CSS.)

- Word-spacing:
 Establece la separación entre palabras, (se puede establecer en cualquier medida valida para CSS.)

- Line-Height:
 Establece el alto de cada linea,( se puede dar una medida concreta o se puede poner en un número que se multiplicara por el font size del texto al que se lo estemos aplicando)

  - Truco para centrar VERTICALMENTE (POCOS CASOS)
  ```css
  .box{
    background-color: lime;
    /* Para poder hacer este truco necesitamos conocer (La altura del contenedor)
    y que el texto no sea de mas de una linea */
    height: 200px;
    }

  /* Le colocamos la misma altura del contenedor y se centrara (recordemos que no debe ser de mas de una linea) */
  .word{
    line-height: 200px;
  }
  ```
  - Si el alto del contenedor cambia, se rompe el TRUCO (Con variables se pueden solucionar).

  - Si hay mas de una linea tambien se rompe

  - NO ME PARECE MUY UTIL LA VERDAD

## Orientación del texto.

- Writing-mode: Establece la dirección del texto

  - Existen varios valores, las mas utilizadas son, vertical-lr y vertical-rl (Tambien se rotan las letras)

- Si queremos escribir en vertical, sin rotar las letras utilizamos esta propiedad
  ```css
    .text{
      /*Rompemos las palabras y se ven en vertical*/
      word-break: break-all;
      width: 10px;
      /*Para que quede centrado*/
      text-align:center;
    }
  ```
# FINAL DEL CURSO UwU

## Donde NO buscar información
  - **W3Schools:** En la opinion de Dorian es una MIERDA

## Donde SI buscar información
  - **MDN:** Siempre busquemos en la MDN, es la documentación OFICIAL.

  - **CSS-TRICKS:** No es documentación oficial, pero da muy buenos consejos y trucos

  - **Can I Use:** Nos muestra el soporte de las propiedades de CSS en los navegadores.

  ## ¿Que hago ahora?

  - Practicas de HTML y CSS (Dorian tiene un video de practicas)

  - Hacer el Curso de CSS Intermedio y SASS

  - Aprender JavaScript

  - PRACTICAR MUCHO 
