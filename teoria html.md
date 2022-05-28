# 1. Vocabulario web

- IP => Identificadaor unico numerico de una pagina web

- Dominio => Nombre de la pagina web EJ: google.com

- DNS => Server que tiene la función de traducir el nombre del dominio a su IP o viceversa

  - IP => DNS => DOMINIO
  - DOMINIO => DNS => IP

- Sitio web => Un conjunto de paginas web alojadas en un mismo dominio

- Servidor web => Un ordenador que solo recibe peticiones y devuelve lo que le piden

- Hosting => Almacenamiento del servidor web (El almacenamiento que uno contrata para alojar el sitio web)

- Petición => La acción de pedir recursos al servidor web

# 2. Que es HTML

Es un lenguaje de marcado de hypertexto, cuyo objetivo es indicar al navegador y a los motores de busqueda, cual es la estructura de nuestra pagina web y de que se trata.

Por eso es de vital importancia construir una buena estructura de pagina (Solida y con las etiquetas correctas)

# 3. Sintaxis HTML

1. Primeramente para casi todas las cosas de programación se deben evitar los espacios y mayusculas en las carpetas.

Se deben de usar las etiquetas correctas para que la estructura no quede mal, esto ayuda a entender al navegador

## Estructura base

```HTML
<!-- Esto define el Estandar HTML5 -->
<!DOCTYPE html>

<!-- Idioma de la pagina-->
<html lang="es">
<head>
   <!-- Codificación del lenguaje que usaremos -->
  <meta charset="UTF-8">

  <!-- El resto lo veremos luego -->
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>

</body>
</html>
```

# 4. Titulos y parrafos

## Titulos

Hay 6 niveles de encabezados y van del mas importante al menos importante

- h1 => Mas importante
- h2
- h3
- h4
- h5
- h6 => Menos importante

NADA DE ESTO Y EN GENERAL DE HTML SE USA PARA DAR ESTILOS PARA ESO EXISTE CSS.

Otra cosa muy importante es que no se pueden saltar niveles de H, es decir NO puedo pasar de:

- h1 a h3
- h2 a h4
- etc....

Despues de un h1 si se requiere se debe tener el h2 y asi sucesivamente.

EJEMPLO

```HTML
<!-- Lo principal y mas importante -->
<h1>HARRY POTTER</h1>

<!-- Todos los "h2" estan al mismo nivel -->
<h2>Sinopsis</h2>
<h2>Novelas</h2>
    <!-- Dentro de los h3 podrian ir h4 y etc -->
    <h3>La priedra filosolal</h3>
    <h3>Camara de los secretos</h3>
    <h3>Prisionero de Azkaban</h3>
    <h3>El caliz del fuego</h3>
    <h3>La orden del fenix</h3>

<h2>Peliculas</h2>

```

## Parrafos

Es un parrafo (Elemento de bloque en el que se coloca texto)

PD: "Lorem" es un texto en latin que se usa para rellenar

```HTML
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi culpa beatae veniam eius autem harum, alias ab laboriosam quae atque accusamus, illo, enim nihil. Ut natus fugit rerum commodi aliquid!</p>
```

# 5. Header, Main Footer

- ## Header (Encabezado)

  - Normalmente van los menús de navegación, logo de la pagina, redes sociales, entre otras cosas.

  ```HTML
  <header>
  <!-- Menu de navegacion,logo, redes sociales etc... -->
  INICIO - CONTACTO - INFORMACION - CATALOGO
  </header>
  ```

- ## Main (Contenido principal)

  - Aqui va todo el contenido principal de la pagina.

  ```HTML
  <main>
  <h1>Harry Potter</h1>

    <h2>Sinopsis</h2>
    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Distinctio optio quos commodi inventore aperiam, sapiente natus magni perferendis itaque exercitationem assumenda! Consequatur nam, quasi maiores accusantium culpa nulla fuga iusto!</p>

    <h2>Novelas</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Reiciendis blanditiis eligendi, placeat tempore magni assumenda? Unde est cumque dignissimos, molestias sequi ut quaerat corrupti illo, voluptatibus officiis nesciunt voluptatem aperiam!</p>
  </main>
  ```

- ## Footer (Pie de pagina)

  - Aqui va el pie de pagina como la información de contacto o cosas similares

  ```HTML
  <footer>
    <!-- *Aca tendria que ir el pie de pagina -->
    Curso de HTML de Youtube 2020-2021
  </footer>

  </body>
  </html>
  ```

# 6. Section y article (IMPORTANTE)

## Section

Es un contenedor generico que agrupa contenido que esta relacionado. Bloques de contenido.

## Article

Es un contenedor que representa contenido independiente

## Aside

Se utiliza para representar contenido relacionado pero que no forma parte del contenido principal

## Datos importantes de los 3

- "Section" puede contener dentro varios "Article".

- "Article" puede contener dentro varios "section".

- Los "Article" pueden tener header y footer aunque no es obligatorio.

- Tambien pueden existir "Section" con mas "Section" dentro

# 7. Elementos de BLOQUE y elementos de LINEA

## Elementos de BLOQUE

Ocupan todo el ancho disponible AUNQUE su contenido no lo ocupe. Es decir ocupan todo el espacio asi no lo necesiten

EJEMPLO:

```HTML
<!-- Son elementos de bloque -->
<h1>Capitulo Primero</h1>
<p>Que trata de la condición y ejercicio del famoso higaldo</p>
<!-- Todas las etiquetas que hemos visto hasta el momento son de BLOQUE -->
```

![Elem. de bloque](/assets/Elemento%20de%20bloque.png)

## Elementos de LINEA

Estos elementos ocupan unicamente el espacio que ocupe su contenido.

EJEMPLO:

```HTML
<!-- Elementos de linea -->
<span>Soy un elemento de linea</span>
```

![Elem. de bloque](/assets/linea-bloque.png)

# 8. Elementos de Linea I

Ahora vamos a ver las etiquetas de linea definitivamente importantes

- Em => Representa enfasis, sirve para decirle al navegador que algo tiene mas importancia que el resto del texto.
- Strong => Representa aún MAS enfasis que "Em", sirve para decirle al navegador que lo que esta dentro de "strong" es mas importante que incluso lo de "em".
- Small => Tiene MENOS enfasis de lo normal, le dice al navegador que algo es menos importante que el resto.

```HTML
<p> <em>El dinero</em> es importante pero <strong> la salud </strong> es lo mas importante <small>Saludos</small></p>
```

Si fueran valores numericos

- small = -1
- p = 0
- em = 1
- strong = 2

---

Otras etiquetas de linea importantes son:

- br => Sirve para forzar un salto de linea (Se parece a "\n") PD: JAMAS se debe utilizar para dar espacios, eso es algo estetico y se hace con CSS

- wbr => Da un salto de linea (SOLO SI ES NECESARIO HACERLO), Si el navegador tiene que hacer un salto de pagina si o si "wbr" indica por donde se tiene que partir la palabra para que no pierda coherencia, por lo general es muy dificil que exista una palabra tan larga pero si por ejemplo con URL PD: El "-" equivale a "wbr".

```HTML
<p>lorem no se que en latin xd</p>
<!-- Forzamos salto de linea -->
<br>
<!-- Si la URL no cabe en una linea se va a partir por los lados de "wbr" -->
<p>http://127.0.0.1:5500/<wbr>html/<wbr>practicas/<wbr>tutorial/<wbr>mlaaaaaaelementos_de_linea.html</p>
```

# 9. Elementos de Linea II

- Time => Se utiliza para representar fecha y hora, visualmente no notaremos diferencia, pero el navegador le dara la IMPORTANCIA SEMANTICA. PD: Es valido tambien solo con fecha o solo con hora.

```HTML
<!-- * Para darle la importancia semantica de una fecha/hora -->
    <time> 01/03/2022 11:33</time>
    <time> 01/03/2022</time>
    <time> 11:33</time>
```

- italic,bold,underline => Son pensadas UNICAMENTE para dar estilos, aparecieron a inicios de HTML cuando aún no existia CSS, ahorita ya no se usan para nada, excepto quizas "italic" que lo podemos usar con librerias de iconos, de resto es mejor hacerlo con CSS.

```HTML
<!-- Etiquetas que ya no se usan -->
<i>Italic</i>
<b>Bold</b>
<u>Underline</u>

<!-- Unico uso probable a la etiqueta "i" -->
<i class="fab fa-500px"></i>
```

- sub-sup => Es el subindice y el superindice, aunque es probable que la utilicemos muy poco

```HTML
<!-- El numerito chiquito arriba del numero -->
<p>4 Elevado al cuadrado se representa asi
4<sup>2</sup></p>

<!-- El numerito chiquito abajo del numero -->
<p>El agua oxigenada tiene la formula H<sub>2</sub>O<sub>2</sub> </p>
```

# 10. Atributos

Los atributos son valores adicionales que configuran los elementos o su comportamiento. Existen 2 tipos:

- Atributos normales (atributo = valor), es necesario pasarle un valor para que funcione.

- Atributos booleanos (atributo), si el atributo es invocado su valor siempre sera TRUE

Atributos importantes:

- lang => configura al elemento html y define el lenguaje de la pagina web

- charset => Codificación de caracteres de HTML

- class => Crea una clase en el HTML esto para dar estilos a las cosas atraves de CSS, como si fuera un "identificador", es muy importante y muy usado.

- id => Es un identificador de elementos, se usa para dar comportamientos atraves de JS (JavaScript)

- title => Da como una cajita de descripción en la pagina web

- data => Nos permite guardar algún valor en la etiqueta (No le ví ningún uso pero dice que si va a servir especialmente en JAVASCRIPT)

EXISTEN MUCHOS MAS ATRIBUTOS QUE SE IRAN APRENDIENDO A MEDIDA QUE SE USEN LOS ELEMENTOS

# 11. Enlaces (Links)

## Introducción

Son la parte mas IMPORTANTE de la web, pues le da el funcionamiento a esta. su objetivo es conectar una pagina o sitio web con otra.

Los links se establecen con el elemento "a" que a su vez tiene el atributo "href"

- En el atributo "href" se coloca el enlace o la ruta para ir al otro sitio web

```HTML
<!-- Asi es un enlace -->
<a href="ruta a donde queremos ir" >nombre del enlace</a>
<!-- EJEMPLO -->
<a href="https://www.google.com" >Ir a google</a>
```

## Rutas absolutas y relativas

### Rutas absolutas

Tienen un protocolo "http" o "https" se suelen utilizar para rutas EXTERNAS, tenemos que salir fuera de nuestro proyecto a buscar la dirección

Ejemplo:

```html
<!-- Tenemos que salir de nuestro proyecto a buscar la ruta -->
<a href="https://www.google.com">Ir a google</a>
```

### Rutas Relativas

Las rutas relativas, pueden ser relativas al punto donde estemos o relativas a la raiz de nuestro proyecto.

Ejemplo:

```html
<!-- Al punto donde estemos -->
<a href="contacto.html">Ir a contactos</a>
<!-- A la raiz del proyecto -->
<a href="/Enlaces/contacto.html">Ir a contacto</a>
```

**PD: "index.html" es el archivo por defecto intentan cargar los servidores y los navegadores cuando cargan un proyecto, lo mejor es que el archivo principal siempre se llame "index.html"**

## Atributos mas importantes

- target => Va a definir como se abre el enlace, sus valores son:

  - \_self => Por defecto lo abre en la misma pestaña (Cuando abramos enlaces de nuestro proyecto lo mejor es que sea en la misma pestaña)
  - \_blank => Lo abre en otra pestaña (Cuando abramos webs de otros lo mejor es que sea en otra pestaña)

- download (boolean) => Sirve para cuando se clickee se descargue algo, IMPORTANTE: el recurso debe estar en tu mismo server.

**PD: Un HTML con imagenes, videos etc.. estos archivos deben estar en una carpeta llamada assets con estos recursos**

## Navegación con Anclas

La navegacion con anclas sirve para moverse entre puntos de la misma pagina (Como un indice en wikipedia)

Para hacer esto, el elemento al cual queremos ir debe tener el atributo "ID" y para movernos usamos la etiqueta "a" y en su "href" colocamos el id asi "#id"

EJEMPLO:

```html
<!-- Asi es la navegacion con anclas -->
<a href="#id">Ir a tal punto</a>

<!-- Ejemplo-->
<a href="#post-1">Ir a post 1</a>

<!-- Si queremos ir a un punto especifico pero de otra pagina -->
<a href="/index.html#post-1">Ir a post 1</a>
```
# 12. Introducción a las listas
Sirven para listar contenido en función al tipo de contenido que queremos listar

Tenemos 3 tipos de lista:
* ul => **unordered list**: Se utilizan cuando no importa el orden de los elementos (EJ: Lista de compras)
```html
<ul>
  <!-- Li es utilizado para colocar elementos -->
    <li>Arroz</li>
    <li>Pan</li>
    <li>Leche</li>
    <li>huevos</li>
  </ul>
```
* ol => **ordered list**: Se utilizan cuando el orden SI importa (EJ: Top 10)
```html
<!-- Lenguajes a aprender en orden -->
 <ol>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
  </ol>
```
* dl => **definition list**: Se utiliza para hacer una lista de definiciones (EJ: Diccionario)
```html
 <!-- <dt> Termino que vamos a definir -->
 <!--<dd> Definición del termino  -->
  <dl>
   
    <dt>HTML</dt>
    <dd>HyperText Markup Languaje: Es un lenguaje de marcado y estructura</dd>

    <dt>CSS</dt>
    <dd>Cascade Style Sheets: Es un lenguaje de diseño que sirve para dar estilos al HTML </dd>

    <dt>JavaScript</dt>
    <dd>Es un lenguaje de programacion para dar interactividad a un sitio web</dd>
  </dl>
```
## Listas anidadas
Es posible tener una lista dentro de otra y asi infinitamente
```html
<ul>
  <li>
    HTML
    <ol>
      <li>Estructura</li>
      <li>Sintaxis</li>
      <li>Etiquetas</li>
    </ol>
  </li>
</ul>
```
## Atributos de las listas
### Listas ordenadas 
type => Estilo de enumaración (1,a,I,A)
start => Inicio de la secuencia (Desde que numero queremos que inicie la lista)
### Listas Desordenadas
type => Estilo de los items (circulo, cuadrado..., Esto se hace casi siempre desde CSS)

# 13.  Introducción a las tablas 
Sirven para mostrar un contenido de forma tabulada
## Etiquetas necesarias
* Table => Encierra una tabla 
* tr => **Table row:** Construye una fila
* td => **Tabla data:** Construye una celda
* Caption => Para los titulos de las tablas (OPCIONAL)
* thead => Para establecer las cabeceras de la tabla, cuando queremos establecer una celda como cabecera usamos "th" en lugar de "td"
* tbody => Es el cuerpo de la tabla, es OPCIONAL mientras no utilizemos THEAD, si lo utilizamos, TBODY se vuelve obligatorio
* tfood => Sirve para colocar un pie de tabla es completamente OPCIONAL

## Atributos de las tablas
* Rowspan => Sirve para que una celda ocupe mas de una fila, el valor por defecto es 1

* Colspan = Sirve para que una celda ocupe mas de una Columna, el valor por defecto es 1

PD: Hay que tener muy en cuenta como agrandamos las celdas, porque de hacerlo mal puede ROMPER la tabla

## Seleccionar Columnas (Colgroup & col)
* Para seleccionar una fila tenemos "TR" pero a la hora de seleccionar una columna es mas dificil

* Para seleccionar una columna tenemos la etiqueta **"Colgropup"** y dentro de esta usamos la etiqueta **"col"** la primera etiqueta **"col"** equivaldra a la primera columna y asi respectivamente con todas

* Si necesitamos que una etiqueta **"col"** abarque mas de una COLUMNA usaremos el atributo span.
  ```html
  <!-- # de columnas que queremos que abarque -->
  <col span="3"> 
  ```


## EJEMPLO
 ```html
 <table>
   <!-- Titulo de la tabla -->
    <caption>Horario de Clases</caption>

    <!-- Para seleccionar las columnas -->
    <colgroup>
      <col>
      <col>
      <col>
      <col>
      <col>
      <col>
    </colgroup>


    <!-- Fila de enzabezado de la tabla-->
    <thead>
      <tr>
        <!-- Celdas encabezado (van con TH) -->
        <th>Hora/Dia</th>
        <th>Lunes</th>
        <th>Martes</th>
        <th>Miercoles</th>
        <th>Jueves</th>
        <th>Viernes</th>
      </tr>
    </thead>

    <!-- Cuerpo de la tabla -->
    <tbody>
      <!-- Fila y celdas regulares -->
      <tr>
        <td>9:00</td>
        <td>Lengua</td>
        <td>Sociales</td>
        <td>Edu.Fisica</td>
        <td>Lengua</td>
        <td>Lengua</td>
      </tr>
      <tr>
        <td>9:45</td>
        <td>Naturales</td>
        <td>Lengua</td>
        <!-- Atributo rowspan para ocupar 2 filas -->
        <td rowspan="2">Lengua</td>
        <td>Sociales</td>
        <td>Naturales</td>
      </tr>
      <tr>
        <td>10:30</td>
        <td>Edu.Fisica</td>
        <td>Ingles</td>
        <td>Alternativa</td>
        <td>Matematicas</td>
      </tr>
      <tr>
        <td>11:15</td>
        <td>Ingles</td>
        <td>Plasticas</td>
        <td>Naturales</td>
        <td>Ingles</td>
        <td>Ingles</td>
      </tr>
      <tr>
        <td>12:00</td>
        <!-- Atributo colspan para ocupar mas 5 columnas -->
        <td colspan="5">Recreo</td>
      </tr>
      <tr>
        <td>12:30</td>
        <td rowspan="2">Ingles</td>
        <td>Matematicas</td>
        <td>Matematicas</td>
        <td>Matematicas</td>
        <td rowspan="2">Matematicas</td>
      </tr>
      <tr>
        <td>13:15</td>
        <td>Biblio</td>
        <td>Musica</td>
        <td>Tecnologia</td>

      </tr>
    </tbody>
    <!-- Pie de tabla -->
    <tfoot>
      <tr>
        <td colspan="5">Total de asignaturas</td>
        <td>10</td>
      </tr>
    </tfoot>
  <!-- Fin de la tabla -->
  </table>
 ```
# 14. Etiquetas IMPORTANTES de bloque
* Address => Se utiliza para dar información de contacto para el body o el article mas cercano
  ```html
  <address>
    <!-- Semanticamente seria mejor -->
    Tony Stark <br>
    Malibu <br>
    90265 <br>
    California
  </address>
  ```
* blockcuote => Se utiliza para amrcar la citas a otros autores o documentos
  * Recibe el atributo "cite" para poner el enlace al documento original (OPCIONAL) **solo sirve para que el navegador sepa de donde viene**, no lo convertira en un enlace
  * Existe una alternativa de etiqueta en linea pero por el momento esta es de bloque 
  ```html
    <blockquote cite="https://lamenteesmaravillosa.com/25-frases-del-maravilloso-mario-benedetti/">
    <p>“No te rindas, por favor no cedas, aunque el frío queme, aunque el miedo muerda, aunque el sol se esconda, y se calle el viento, aún hay fuego en tu alma, aún hay vida en tus sueños. Porque la vida es tuya y tuyo también el deseo, porque cada día es un comienzo nuevo, porque esta es la hora y el mejor momento, porque no estás solo, ¡porque yo te quiero!”</p>
    </blockquote>
  ```
* pre => Se utiliza para tener el codigo preformateado, representado igual como se escribio en el codigo

```html
<!-- Se mostrara tal cual -->

<pre>
  Hola,
  ¿qué tal?
  Este contenido
  se muestra exactamente
  igual de como se escribe en el
  HTML
</pre>

```
* div => Es simplemente una división del documento, no significa nada, es un contenedor generico, y se usa principalmente para dar estilos (Lo ideal es que dentro del div el contenido este relacionado)

* hr => Le dice al navegador que vamos a cambiar de tema (De lo que estamos hablando)

# 15. Etiquetas IMPORTANTES de linea
* span => Es un contenedor de linea, equivalente a div, se suele usar para encerrar palabras o pequeños textos y darles estilos, semanticamente no significa nada 
* q => Es el equivalente a "blockquote" pero de linea, marca citas de otros documentos
* code => Encierra codigo que queremos se represente visualmente como en el HTML, se suele usar junto a la etiqueta **"pre"**
  * Es como decirle al navegador que lo que pusimos es codigo

**CODIGO ASCII:** Se usa para hacer caracteres especiales

# 16. Introducción a Formularios
