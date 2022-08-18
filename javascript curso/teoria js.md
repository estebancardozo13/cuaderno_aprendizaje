# 1. Historia de JavaScript

-   Es un lenguaje de programación que sirve para la web, y el unico que puede interpretar un navegador
-   Antes del 2009 no era muy importante y se burlaban de el lenguaje
-   Actualmente con node.js podemos hacer tambien back-end
-   En el 2015 salio ECMAScript 6 que revoluciono el lenguaje

## Tecnologias descendientes de JavaScript MAS IMPORTANTES

-   Ajax => Obtener información del server
-   jQuery => Ya no es necesario y es pesada
-   nodeJS => Permite ejecutar JS desde un server
-   JSON => Sustituye el XML

## Frameworks MAS IMPORTANTES

-   Angular
-   React
-   VueJs

# 2. Sintaxis y tipos de datos

## Sintaxis (Condiciones)

-   Es case sensitive
-   Es de tipado débil o dinamico
-   Las sentencias finalizan con ;
-   Los bloques finalizan con } y se puede colocar despues un ; (Opcional)

## Variables y constantes

-   Es lo mismo que en otro lenguaje de programación
-   Para declarar una variable se usa la palabra reservada "let", NO es RECOMENDABLE usar "var" porque genera problemas
-   Para declarar una constante se usa la palabra reservada "const"

## Scope o Ambito

-   Es la zona (el sitio) donde existe nuestra variable o cosntante - Es decir dentro de un bloque etc...

# 3. Operadores en JavaScript

-   Son los operadores de toda la vida
-   "a++" Primero devuelve la variable y luego la incrementa
-   "++a" Primero incrementa la variable y luego la devuelve

# 4. Metodos y propiedades de los String

-   Los metodos es todo aquello que la cadena puede hacer
-   Las propiedades son la caracteristicas de las cadenas

## Template String (format string)

Estan creados para las situaciones de combinar variables en un mismo mensaje

-   Se puede hacer uso de estos colocando 2 acentos graves en vez de comillas, como escribiendo codigo en markdown

```js
console.log(`Hola ${nombre} ${apellido}. Tienes ${edad} años.`);
```

# 5. Objeto Math

Es un objeto que se utiliza para operaciones matematicas mas especificas (Tambien utiliza la nomenclatura del ".")

## Metodos

Tiene muchos metodos pero los principales son:

-   Math.abs(x) => Devuelve valor absoluto de x
-   Math.ceil(x)=> Redondea hacia abajo
-   Math.floor(x) => Redondea hacia arriba
-   Math.pow(x,y) => Devuelve la potencia de x elevado a y
-   Math.random() => Devuelve un numero aleatorio entre 0 y 1
-   Math.round(x) => Redondea al entero mas cercano
-   Math.sign(x) => Devuelve el signo de x, si es negativo o positivo

```js
console.log(Math.abs(-8));
console.log(Math.ceil(8.7));
console.log(Math.floor(8.7));
console.log(Math.pow(3, 2));
console.log(Math.random());
console.log(Math.round(3.5));
console.log(Math.sign(-3));
```

## Hacer un numero aleatorio entre 0 y un numero mayor a 1 (que sea entero)

```js
// Numero aleatorio entero entre 0 e indefinido
console.log(Math.random() * 100);
// Numero aleatorio definiendo limites entre maximo y minimo
console.log(Math.round(Math.random() * (10 - 5) + 5));
```

# 6. Condicionales

Absolutamente igual a lo común

# 7. Ordenar 3 numeros de mayor a menor (Con condicionales)

```js
let a = 10;
let b = 30;
let c = 20;

if (a >= b && a >= c) {
    if (c >= b) {
        console.log(a, c, b);
    } else {
        console.log(a, b, c);
    }
} else if (b >= a && b >= c) {
    if (a >= c) {
        console.log(b, a, c);
    } else {
        console.log(b, c, a);
    }
} else if (c >= a && c >= b) {
    if (a >= b) {
        console.log(c, a, b);
    } else {
        console.log(c, b, a);
    }
}
```

# 8. Condicional Switch

Se utiliza para elegir un camino de varios preestablecidos. Tenemos 3 tipos principales:

-   Sintaxis Simple
    -   Ejecuta un codigo diferente dependiendo del caso
-   Sintaxis multiple
    -   Puede ejecutar un mismo codigo en una serie de casos
    ```js
    switch (num) {
        case 1:
        case 2:
        case 2:
            // Codigo para esos 3 casos
            break;
    }
    ```
-   Sintaxis Multiple encadenada (No nos explica, por que no se usa mucho )

# 9. Operador Ternario

-   Puede tener una sentencia o varias

    -   (condición)? true:false

    ```js
    let num = 0;

    // Operador ternario
    num % 2 == 0 ? console.log(`${num} es par`) : console.log(`${num} es impar`);
    ```

# 10. Arrays

-   En JavaScript nos permiten almacenar VARIOS TIPOS de datos en un mismo Array, sin embargo hacer esto NO ES RECOMENDABLE
-   Se declaran con llaves cuadradas o corchetes []
-   Pueden añadirse o eliminarse elementos (Como una lista)

# 11. Arrays II

-   length => longitud del array
-   push => Añade elementos al final y devuelve la longitud (es opcional usarla)
-   unshift => Añade elementos al principio del array y devuelve su longitud
-   reverse => Le da la vuelta al array
-   splice => elimina desde posiciones

# 12. Bucle While - Do-While

Exactamente lo mismo de siempre

# 13. Bucle For

-   La i de variable viene de INCREMENTO
-   De resto es todo igual a lo que conocemos

# 14. Bucles for of / for in

Simplifica el bucle for tradicional sin tener que darle un número de vueltas ni realizar un incremento

## Bucle "for of"

```js
let names = ["paco", "jose", "paula", "maria"];

// Bucle "for of" identico al bucle "for each"
for (let name of names) {
    console.log(name);
}
```

## Bucle "for in"

```js
let names = ["paco", "jose", "paula", "maria"];

// El bucle "for in" imprime es el indice del array
for (let index in names) {
    console.log(name);
    // Aca imprimira 0,1,2,3,4 (Hasta el ultimo indice del array)
}
```

-   Break => Rompe el bucle
-   Continue => Se salta la posicion que lo tenga y sigue el bucle

# 15-16 Ejercicio de repaso

Hicimos alguno ejercicios para repasar lo anterior

# 17. Objetos(Introducción)

Son estructuras de datos que representan propiedades, valores y acciones que puede realizar el objeto.

Todos los objetos tienen propiedades o atributos (color, material,etc) y comportamientos o acciones (Arrancar, acelerar, frenar, etc...) representados por pares de clave (key): valor (value)

**EJEMPLO**

Asi se declara un objeto y se le asignan propiedades.

```js
// Objeto Computador
const = {
    screenSize:17,
    model: 'MacBook Pro'
}
// Objeto Mesa
const table = {
    material:'wood',
    width:160,
    height:110
}
// Los comportamientos se representan a traves de funciones, por eso no estan aquí
```

## Acceder a las propiedades

Para acceder a las propiedades y acciones del objeto se utiliza la nomenclatura del punto

**EJEMPLO**

```js
// Objeto Persona
const person = {
    name: "Juan",
    age: 26,
    sons: ["Laura", "Diego"],
};
// Acceder a las propiedades
console.log(person.name);
console.log(person.age);
console.log(person.sons[0]);
console.log(person.sons[1]);

// Cuando tengamos demasiadas propiedades de un objeto, podriamos utilizar un bucle para recorrer el objeto.

for (const key in person) {
    // Aca imprime al claves (name, edad, sons)
    console.log(key);
    // Aca imprime los valores de esas claves (Tratamos el objeto como si fuera array, PERO no lo es)****
    console.log(person[key]);
    // Se debe pasar como string, sino piensa que es una variable
    console.log(person["name"]);
}
```

**NOTA: Es muy importante diferenciar arrays de objetos, los objetos son con llaves, los arrays con corchete cuadrado**

**IMPRIMIR EL ARRAY DE LOS HIJOS**

```js
// Utilizamos for of porque queremos imprimir los valores.
for (const son of person.sons) {
    console.log(son);
}
```

# 18. Funciones(Introducción)

Son fragmentos de codigo que escribimos para ejecutar una tarea y no volver a escribir el mismo código más de una vez.

-   Nos ayuda a modularizar el codigo (Ayuda bastante a localizar errores)

-   Las funciones deben realizar una sola tarea.

**SINTAXIS**

```js
// Sintaxis de una función

// Hasta hace 3 años se utilizaba asi:
function nombreFunción() {
    // Codigo a ejecutar
}

// Con ECMAScript6 esta es la nueva sintaxis, que soluciona muchos problemas que podriamos tener

// NO siempre es asi pero si en su gran mayoria
// Se le conoce como función de flecha
const nombreFunción = () => {
    // Codigo a ejecutar
};
```

-   Una función puede recibir parametros, (Es lo que va a utilizar la función para ejecutarse) y es opcional.
    -   Podemos mandar desde 0 parametros, hasta los que necesitemos(No hay limite).

```js
// Sintaxis de una función con parametros

// Como era antes con function
function nombreFunción(param1, param2) {
    // Codigo a ejecutar
}

// Como es ahora con función de flecha
const nombreFuncdón = (param1, param2) => {
    // Codigo a ejecutar
};
```

-   Las funciones pueden devolver valores, lo habitual es que devuelva algún valor. En algunos casos quizas no necesitemos que devuelva nada, solo que ejecute el codigo que esta dentro.

```js
// Sintaxis de una función que retorna algo

function nombreFunción(param1,param2){
    return param1+param2;
}

// Función de flecha (si solo tenemos una instrucción)
const nombreFunción = (param1+param2) => param1+param2;
```

**NOTA: Hay varias exepciones con el tema de las funciones de flechas que vamos a ir afianzando, entonces queda aprender mas sobre como usarlo correctamente**

## Ejemplos

**Funcion Saludar**

```js
// Se crea la función (De forma anterios)
function saludar() {
    console.log("Hola");
}

// Creamos función de saludar usuario, con una función de flecha
const saludarUsuario = (user) => console.log(`Hola ${user}`);

// Se invoca la función (Ambas se invocan iguales)
saludar();
saludarUsuario("Sergio");
```

**Funcion Sumar**

```js
const suma = (num1, num2) => {
    // Si colocamos las llaves, debemos utilizar "return" para retornar algo si o si.
    return num1 + num2;
};

console.log(suma(3, 2));
```

**Función sumar con condicional**

```js
const suma = (num1, num2) => {
    if (num1 == 2) {
        // Una vez que la función encuentre un "return" deja de ejecutar todo lo demas
        return num1 + num2;
    }

    return num1;
};
console.log(suma(3, 2));
```

**NOTA: Las funciones se consideran objetos de primera clase, por lo que con una funcion podemos hacer lo que queramos. EJEMPLO: Que se puede guardar lo que devuelve en una variable (Me imagino que tiene otras utilidades.)**

# 19. POO - Clases

Es un paradigma de la programación que actualiza la forma de programar que teniamos antes

**Paradigma de programación:** _Es una forma de darle solución a un problema_

Algunos de los conceptos fundamentales de la POO son:

-   Clases
-   Herencia
-   Objeto
-   Método
-   Evento
-   ETC...

## Clases

Es una plantilla que sirve como molde para crear objetos iguales.(Las clases se implementaron con ECMAScript6)

Cuando creamos un objeto, a esa acción se le denomina INSTANCIAR un objeto.

En las clases necesitamos una función constructora. Se tiene que llamar constructor y se ejecuta CADA VEZ que creemos un objeto.(Se les sinvoca de una forma especial).

**EJEMPLO**

```js
// Clase Persona
class Person {
    // Constructor con las propiedades necesarias para crear el objeto Person
    //Es obligatorio que se llame constructor
    constructor(name, surname, age) {
        this.name = name;
        this.surname = surname;
        this.age = age;
    }
}
```

### This

Hace referencia al objeto que creamos.

-   nombre del objeto = nombre del parametro.
-   apellido del objeto = apellido del parametro.
-   edad del objeto = edad del parametro.

Se le pueden asignar propiedades que no haya en los parámetros, pero SIEMPRE utilizando "this" para referenciar el objeto

```js
this.datos = `${nombre} ${apellido} ${edad}`;
```

## Metodos

Los objetos pueden tener funciones asociadas a él. En ese caso se les denomina MÉTODOS.

Se pueden crear dentro de la clase (Fuera del constructor) podemos crear metodos asociados al objeto

```js
saludar(){
      return `Hola, me llamo ${this.name} y tengo ${this.edad} años`
  }
```

## Objetos (Crear Objetos)

Para crear un objeto utilizando la clase o plantilla se hace con la palabra reservada "new" y el nombre de la clase queremos utilizar.

**EJEMPLO**

```js
const esteban = new Person("Esteban", "Cardozo", 19);
```

Una vez INSTANCIADO el objeto podremos acceder a sus propiedades y métodos utilizando la nomenclatura del punto o buscando su propiedad en el objeto.

**EJEMPLO**

-   Con la nomenclatura del punto.}

```js
esteban.name;
esteban.surname;
esteban.age;
esteban.datos;
esteban.saludar();
```

-   Buscando su propiedad en el objeto

```js
esteban["name"];
esteban["surname"];
esteban["age"];
esteban["datos"];
// Para hacer entender al programa que se trata de una función
esteban["saludar"]();
```

## EJEMPLO GENERAL

```js
class Person {
    constructor(name, surname, age) {
        this.name = name;
        this.surname = surname;
        this.age = age;

        // Aqui no hace falta usar el this, porque lo agarra directamente del parametro
        this.data = `Me llamo ${name} ${surname} y tengo ${age} años`;
    }

    // Despues del constructor podemos crear todos los metodos que queramos

    // Su sintaxis debe ser OBLIGATORIAMENTE asi (No esta permitido usar "function" ni flechas):
    saludar() {
        return `Hola, me llamo ${this.name} y tengo ${this.age} años`;
    }
}

// Instanciamos el objeto Esteban
const esteban = new Person("Esteban", "Cardozo", 19);

// Instanciamos el objeto Cristhian
const cristhian = new Person("Cristhian", "Cardozo", 31);

// Estos nuevos objetos tienen todas las propiedades y metodos que tiene su clase.

// Entonces con 1 sola clase tenemos el molde para crear TODOS los objetos PERSON que queramos o necesitemos
```

**NOTA: Con ECMAScript6 es mucho mas facil crear objetos, antes no existian las clases y se hacian con funciones, pero no podia haber una función dentro de otra y era un problemon**

# 20. Clases y objetos - Practica Guiada.

**Enunciado:**

1. Crea una clase libro
2. La clase libro tendra titulo, autor, año y genero.
3. Crea un método que devuelva toda la información del libro.
4. Pide 3 libros y guardalos en un array.
5. Los libros se introduciran al arrancar el programa pidiendo los datos con prompt.
6. Validar que los campos no se introduzcan vacios
7. Validar que el año sea un número y que tenga 4 digitos.
8. Validar que el género sea: aventuras, terror o fantasía
9. Crea una función que muestre todos los libros
10. Crea un función que muesrte los autores ordenados alfabeticamente
11. Crea una función que pida un género y muestre la información de los libros que pertenezcan a ese género usando un el método que devuelve la información.

```js
// La clase esta perfectamente escrita
class Book {
    constructor(title, author, year, gender) {
        this.title = title;
        this.author = author;
        this.year = year;
        this.gender = gender;
    }

    getInformation() {
        return `El libro ${this.title} escrito por ${this.author} fue lanzado el año ${this.year} y pertenece al genero de ${this.gender}`;
    }
}

// Esto esta correcto
let books = [];

// En vez de un ciclo "do-while" usamos "while" midiendo la longitud dl array (Es mucho mejor y nos ahorramos un ciclo "for")
while (books.length < 3) {
    let titleBook = prompt(
        `Por favor ingrese el titulo del libro que desea registrar.`
    );

    let authorBook = prompt(`Por favor ingrese el autor del libro "${titleBook}".`);

    let yearBook = parseInt(
        prompt(`Por favor ingrese el año de lanzamiento del libro "${titleBook}".`)
    );

    let genderBook = prompt(
        `Por favor ingrese el genero al que pertenece libro "${titleBook}".`.toLowerCase()
    );

    if (
        titleBook !== "" &&
        authorBook !== "" &&
        !isNaN(yearBook) &&
        yearBook.length == 4 &&
        (genderBook == "aventura" ||
            genderBook == "terror" ||
            genderBook == "fantasia")
    ) {
        books.push(new Book(titleBook, authorBook, yearBook, genderBook));
    }
}

// Dorian mostró el array, yo imprimo el titulo de los libros
const showAllBooks = () => {
    for (let book of Books) {
        console.log(book.title);
    }
};

const showAuthors = () => {
    let authors = [];
    for (let book of books) {
        authors.push(book.author);
    }
    console.log(authors.sort());
};

// Aca lo que cambio, fue que mando toda la información del libro directamente.
const showGender = () => {
    let gender = prompt("Introduzca el género a buscar");
    for (let book of Books) {
        if (book.gender == gender) {
            console.log(book.getInformation());
        }
    }
    console.log(bookGender);
};
```

A comparación de mi codigo, hubieron mas similitudes que cambios que estan documentados en el codigo. Uno de los cambios mas grandes es que yo use un ciclo "do-while" y un "for", mientras que dorian lo simplifico con un "while" y si es mucho mejor la forma en la que el lo hizo.

Otra cosa con la que me quedo fue la forma en la que hizo cumplir las condiciones, una forma sencilla sin tanto rollo, aunque es verdad que se puede mejorar (La dejo abajo para tenerla presente).

```js
// Sino cumple las condiciones no agrega el libro, por lo que pedira otro, hasta que le pasemos 3 libros que cumplan bien las condiciones
if (
    titleBook !== "" &&
    authorBook !== "" &&
    !isNaN(yearBook) &&
    yearBook.length == 4 &&
    (genderBook == "aventura" || genderBook == "terror" || genderBook == "fantasia")
) {
    books.push(new Book(titleBook, authorBook, yearBook, genderBook));
}
```

En terminos generales muy bien y ya.

# 21 Arrays - Metodos II

## .from(iterable):

Convierte en array el elemento iterable. (Es muy util con DOM y se utiliza muchisimo) **_IMPORTANTE_**

-   Nos permite convertir un NodeList en un array.

```js
let word = "Hola mundo";

// Convierte cada letra de la palabra en un elemento de un array
console.log(Array.from(word));
```

No lo entendemos hasta el momento muy bien, pero sera de gran utilidad.

## .sort(callback):

Ordena los elementos de un array alfabeticamente (Valor Unicode), si le pasamos un callback (es opcional) los ordena en función del algoritmo que le pasemos.

-   Para ordenar los numeros, debemos pasar un callback, de lo contrario los ordenara según el valor unicode y este no es el orden normal.

```js
const letters = ["b", "c", "a", "h", "f", "i", "z"];
const numbers = [1, 4, 100, 300, 7, 5, 20];

// Ordena las letras alfabeticamente
console.log(letters.sort());

// Ordenar los numeros de forma ascendente
console.log(numbers.sort((a, b) => a - b));

/* ¿Que hizo la funcion?
 1. Es una función de comparación (compareFN), le pasamos los parametros "a" y "b" por convención, aunque se pueden llamar como quiera.

 2. Lo que hace este tipo de función es recorrer el "array" a traves de pares, donde empezando "a" seria la posición [0] y "b" la posición [1]

 3. Entonces RESTA "a" -"b"

 4. Si la RESTA da un valor positivo, determina que "a" es mayor que "b"

    Si la RESTA da un valor 0, determina que 'a' y 'b' son iguales.

    Si la RESTA da un valor negativo, determina que 'b' es mayor que 'a'

5. En función de esta comparación que hace, la funcion se encarga de RECOLOCAR los elementos en la posición que debe ir cada numero.

Asi es que va recorriendo el array y con las diferentes devolucones de la función hace que el metodo sort() sepa donde colocar los numeros

NOTA: Si quisieramos ordenar de forma descendente (De mayor a menor) la función seria (a,b)=>b-a;
 */
```

**NOTA: El Valor Unicode es el numero que tienen asignadas las letras**

**NOTA: Callback es simplemente una función que la esta ejecutando, otra función**

## .forEach(callback(currentValue,[index]))

Ejecuta la función indicada una vez por cada elemento del array (Es un tipo de bucle). Debe recibir si o si un "callback" con el "currentValue"

Tambien puede recibir un array y otro argumento, pero no lo vamos a ver por el momento.

```js
const numbers = [12, 25, 47, 84, 98];

// Recorremos el array e imprimimos el elemento, es como el for of, pero con una sintaxis mas sencilla
numbers.forEach((number) => console.log(number));

// Si le pasamos un segundo valor, podemos tambien tener el index, entonces es como un for of y un for in
numbers.forEach((number, index) =>
    console.log(`${number} esta en la posición ${index}`)
);
```

En algunos casos sera muy util y en algunos casos no tanto, pero es importante saber su funcionamiento.

## .some(callback) y .every(callback)

Ambos devueven True o False.

-   **some:** Comprueba si al menos un elemento del array cumple la condición.

-   **every:** Comprueba si TODOS los elementos del array cumplen la condición.

```js
const words = ["html", "css", "javascript", "php"];

// word es el elemento.

// Daria 'true' porque al menos 1 de los elementos tienen una longitud mayor a 5
console.log(words.some((word) => word.length > 5));

// Daria 'false' porque no TODOS los elementos tienen una longitud mayor a 5
console.log(words.every((word) => word.length > 5));
```

## .map(callback)

Transforma todos los elementos del array y devuelve un nuevo array. Lo vamos a utilizar muchisimo con el DOM.

```js
const numbers = [12, 25, 47, 84, 98];

// Esta nuevo array (numbers2) tiene los numeros multiplicados x2
let numbers2 = numbers.map((number) => number * 2);
```

## .filter(callback)

Filtra todos los elementos del array que cumplan la condición y devuelve un nuevo array. Va a ser tambien util en el DOM.

```js
const numbers = [12, 25, 47, 84, 98];

// Este nuevo array (numbers2) tiene unicamente los numeros que son mayor de 40
let numbers2 = numbers.filter((number) => number > 40);
```

## .reduce

Reduce todos los elementos del array a un unico valor, dependiendo la función que ejecute.

```js
const numbers = [12, 25, 47, 84, 98];

// Devuelve un valor con la operación que le pasemos, por ejemplo aqui esta sumando todos los numeros del array (tambien se puede multiplicar, dividir, etc...)

// Recorre el array por pares por lo que recibe 2 parametros
console.log(numbers.reduce((a, b) => a + b));
console.log(numbers.reduce((a, b) => a - b));
console.log(numbers.reduce((a, b) => a * b));
console.log(numbers.reduce((a, b) => a / b));
```

```js
// Este es un ejemplo mas util, utilizando un array de objetos

const users = [
    {
        name:'user 1',
        online: true;
    },
    {
        name:'user 2',
        online: true;
    },
    {
        name:'user 3',
        online: false;
    },
    {
        name:'user 4',
        online: true;
    },
    {
        name:'user 5',
        online: false;
    },
    {
        name:'user 6',
        online: true;
    },
]
// Cuenta la cantidad de usuarios conectados y lo guarda en la variable "cont"
// El 0 al final es el valor que va a tener "cont" como valor inicial (inicializar la variable para que funcione)
const usersOnline = users.reduce((cont,user) => {
    if(user.online) cont++;
    return cont;
},0)

console.log(`Hay ${usersOnline} usuarios conectados`);
```

# 22. Spread Operator (Operador de expansión)

Su sintaxis es '...' y principalmente lo que hace es descomprimir el contenido de un array y enviar valor por valor. Ha venido nuevo con ECMAScript6.

Tiene mas usos que vamos a ver a continuación.

```js
const numbers = [12,25,47,84,98];

// 'Descomprime' el array y nos imprime cada valor del array por separado
console.log(...numbers);

//* Enviar elementos de un array a una función

const addNumbers = (a,b,c) >={
    console.log(a+b+c);
}

let numbersToAdd = [1,2,3];

// En vez de pasarle indice por indice, el spread operator "descomprime" el array y agarra los 3 valores del array
addNumbers(...numbersToAdd);

//* Añadir un array a otro array

let users = ['javier','david','rosa','juan','mercedes'];
let newUsers = ['marta','jaime','laura'];

// En vez de pasar usuario por usuario o usar un bucle, usamos el SPREAD OPERATOR
users.push(...newUsers);

//* Copiar Arrays

// Se simplifica copiar el array con el spread operator
let arr1 = [1,2,3,4];
let arr2 = [...arr1];

// Aunque tambien esta esta forma, sin embargo hay casos en que esto no se puede
let arr3 = arr1;

//* Concatenar arrays

let arr1 = [1,2,3,4];
let arr2 = [5,6,7,8];

// Esta es la forma con el metodo concat
let arrconcat = arr1.concat(arr2);

// Esta es la forma con el SPREAD OPERATOR
arrconcat = [...arr1,...arr2];

//* Enviar un número indefinido de argumentos a una función (parametros REST)

// Cuando no sabemos cuantos parametros tenemos que pasar utilizamos esto que se le conoce como Parametros Rest, que hace parte de las utilidades de spread operator
const restParams = (...numbers)=> {
    // Aca se convierte en un array todos los parametros que les pasemos
    console.log(numbers);
}
// Podemos NO pasarle ningún parametro
restParams();
// O pasarle los que queramos
restParams(1,2,3,54,5,6,77,1);

// Esto se usa cuando llamamos la funcion desde API o bases de datos y no conocemos la cantidad de elementos que necesita la función para trabajar.

//* Libreria Math

    const numbers = [12,25,47,84,98];

    // Descomprime el array para que math pueda evaluar los valores del array
    console.log(Math.max(...numbers));
    console.log(Math.min(...numbers));

//* Eliminar elementos duplicados de un array

    const numbers = [12,25,47,84,98,12,25];

    // El objeto SET no permite elementos duplicados, en este momento esta en el elemento set.
    console.log(new Set(numbers));

    // Si quisieramos que esto fuera un array, lo hariamos con SPREAD OPERATOR.
    console.log([...new Set(numbers)]);
```
# 23. Que es y para que sirve el DOM

**DOM (Document Object Model) - (Modelo de Objetos del documento)**

Es toda la estructura HTML del documento. 

NO es JavaScript, es una API (Aplication Programing Interface) que se utiliza a traves de JavaScript. Es fundamental conocerla porque el 99% que utilizamos JS es para interactuar con el DOM.

## NODOS

Cada parte del documento es un Objeto al que se le conoce como NODO.

Hay varios tipos de nodos (12), los más utilizados son:

- **Element Node** (1) (Cualquier etiqueta HTML)
- **Text Node** (3) (El contenido de la etiqueta)
- **Comment Node** (8) (Cualquier comentario HTML)

El numero al lado del nombre es el numero que devuelve el nodo, cuando estamos averiguando que nodo es.

## Conectando con HTML
Para conectar script con HTML se hace con la etiqueta script

- Se puede abrir la etiqueta y escribir codigo ahí mismo PERO no es nada recomendable (Salvo en casos donde no haya otra alternativa).

- El script siempre debe ir al final justo antes de la etiqueta del cierre del body, para que cuando carguen los scripts ya esten el resto de recursos cargados.
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>DOM</title>
</head>
<body>
    <h1 id="title" class="title">DOM Document Object Model</h1>

<!-- La etiqueta se coloca siempre al final, justo antes de la etiqueta del cierre del body -->
<script src="script.js"></script>

<!-- El atributo "type" ya NO es necesario, aunque si lo vemos es para  -->
<script type="text/javascript">
// NO es recomendable escribir JS en el mismo documento
</script>
</body>
</html>
```
## Interactuando con DOM
 - Cuando intentemos acceder a una etiqueta a traves del DOM son KeySensitive y SIEMPRE van en mayus. las etiquetas.

Comandos Basicos que se pueden hacer en la consola del navegador.

1. Se selecciona el elemento del HTML que queremos averiguar.
2. Con todas las sentencias se usa "$0" **(EJ: $0 nodeType)** *solo sirve en la consola de los navegadores* y se utiliza para acceder al elemento como si fuera un objeto.

- **$0 :** Asi solo. Despliega toda la información que tiene ese NODO (Objeto).

- **$0.id:** Nos devuelve el ID del elemento HTML

- **$0.textContent:** Nos devuelve el contenido de la etiqueta

- **$0.nodeType:** Nos devuelve el numero del tipo del NODO (Si es un nodo de **elemento** nos devolvera 1)

- **$0.nodeName:** Nos devuelve el nombre de la etiqueta, con los nodos las etiquetas son **KeySensitive** y si queremos acceder a un nodo a traves de la etiqueta esta DEBE ir en MAYUSCULA (EJ: H1,P,IMG ...) *En el DOM las etiquetas siempre con MAYUSCULA*

Para acceder a un nodo del texto (el contenido de un nodo de elemento) se hace de esta forma:

-**$0.childNodes[0].nodeType:** Aca estamos accediendo a un nodo de tipo texto

**NOTA: Los Nodos tienen muchisimas propiedades que vamos a ir viendo poco a poco**

# 24. Seleccionar elementos del DOM

Los elementos SIEMPRE se guardan en una constante porque el elemento no va a cambiar

```js
// Acceder a un elemento a traves de su ID
document.getElementById('id');

// Accede al primer elemento que coincida con el selector CSS (document | element)
document.querySelector('selectorCSS');

// Accede a todos los elementos que coincidan con el selector CSS, devuelve un nodeList (document | element)
element.querySelectorAll('selectorCSS');
```
