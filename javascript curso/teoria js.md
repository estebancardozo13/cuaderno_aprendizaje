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

-   **Element Node** (1) (Cualquier etiqueta HTML)
-   **Text Node** (3) (El contenido de la etiqueta)
-   **Comment Node** (8) (Cualquier comentario HTML)

El numero al lado del nombre es el numero que devuelve el nodo, cuando estamos averiguando que nodo es.

## Conectando con HTML

Para conectar script con HTML se hace con la etiqueta script

-   Se puede abrir la etiqueta y escribir codigo ahí mismo PERO no es nada recomendable (Salvo en casos donde no haya otra alternativa).

-   El script siempre debe ir al final justo antes de la etiqueta del cierre del body, para que cuando carguen los scripts ya esten el resto de recursos cargados.

```html
<!DOCTYPE html>
<html lang="es">
    <head>
        <meta charset="UTF-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>DOM</title>
    </head>
    <body>
        <h1 id="title" class="title">DOM Document Object Model</h1>

        <!-- La etiqueta se coloca siempre al final, justo antes de la etiqueta del cierre del body -->
        <script src="script.js"></script>

        <!-- El atributo "type" ya NO es necesario, aunque si lo vemos es para escribir JS en el mismo html -->
        <script type="text/javascript">
            // NO es recomendable escribir JS en el mismo documento
        </script>
    </body>
</html>
```

## Interactuando con DOM

-   Cuando intentemos acceder a una etiqueta a traves del DOM son KeySensitive y SIEMPRE van en mayus. las etiquetas.

Comandos Basicos que se pueden hacer en la consola del navegador.

1. Se selecciona el elemento del HTML que queremos averiguar.
2. Con todas las sentencias se usa "$0" **(EJ: $0 nodeType)** _solo sirve en la consola de los navegadores_ y se utiliza para acceder al elemento como si fuera un objeto.

-   `$0 :` Asi solo. Despliega toda la información que tiene ese NODO (Objeto).

-   `$0.id:` Nos devuelve el ID del elemento HTML

-   `$0.textContent:` Nos devuelve el contenido de la etiqueta

-   `$0.nodeType:` Nos devuelve el numero del tipo del NODO (Si es un nodo de **elemento** nos devolvera 1)

-   `$0.nodeName:` Nos devuelve el nombre de la etiqueta, con los nodos las etiquetas son **KeySensitive** y si queremos acceder a un nodo a traves de la etiqueta esta DEBE ir en MAYUSCULA (EJ: H1,P,IMG ...) _En el DOM las etiquetas siempre con MAYUSCULA_

Para acceder a un nodo del texto (el contenido de un nodo de elemento) se hace de esta forma:

-`$0.childNodes[0].nodeType:` Aca estamos accediendo a un nodo de tipo texto

**NOTA: Los Nodos tienen muchisimas propiedades que vamos a ir viendo poco a poco**

# 24. Seleccionar elementos del DOM

Los elementos SIEMPRE se guardan en una constante porque el elemento no va a cambiar.

-   Los ID se usan para JavaScript y las clases para CSS.

```js
// Acceder a un elemento a traves de su ID
document.getElementById("id");

// Accede al PRIMER elemento que coincida con el selector CSS (document | element). Nos devuelve solo el primero
document.querySelector("selectorCSS");

// Accede a TODOS los elementos que coincidan con el selector CSS, devuelve un nodeList (document | element)
element.querySelectorAll("selectorCSS");
```

## getElementByID

```js
// Va en una constante porque el elemento no va a cambiar
// 2. El parametro va entre comillas porque es un 'string'
const title = document.getElementById("title");

// Si queremos cambiar el texto de algún elemento(Se modifican los valores de forma dinamica)
title.textContent = "Cambiamos el texto";
```

-   **textContent:** Nos permite leer el contenido y editarlo.

## querySelector

```js
// Cuando usamos un querySelector tenemos que pasar un selector de CSS, en caso de que sea la clase seria con el (.) EJ: .class

// De esta forma seleccionamos EL PRIMERO con esta clase
const paragraph = document.querySelector(".paragraph");

// No es necesario siempre que sea 'document' podemos referenciarlo en función de donde queramos buscar. Es como ir bajando de padre a hijo

// No usamos el (.) porque hacemos referencia a un selector de elemento.
const span = paragraph.querySelector("span");
```

El limitante que tiene 'querySelector' es que en principio no se puede acceder a los PseudoElemento desde JS.

Hay una forma de acceder a los PseudoElementos PERO no es de esta forma.

## querySelectorAll

Con esta sobrecarga NO agarramos el primer elemento con el selector, sino que agarramos TODOS los elementos con ese selector('clase') y nos devuelve un NodeList.

```js
// Agarramos todos los elementos con la clase
const paragraphs = document.querySelectorAll(".paragraph");

// Si queremos acceder a un elemento en especifico podemos acceder como un array SIN EMBARGO, un NodeList NO es un Array
paragraphs[0].style.color = "red";

// El map es para que devuelva cada posición de un array con una modificación

// En este caso nos daria ERROR porque NO es un Array es un NodeList
paragraphs.map((p) => (p.style.color = "green"));
```

Si necesitamos que el NodeList se vuelva un Array, podemos utilizar el 'Spread operator' o con 'Array.from'

```js
// CON SPREAD OPERATOR

// agarramos elemento por elemento y lo pasamos al array que seria paragraphsSpread
const paragraphsSpread = [...document.querySelectorAll(".paragraph")];

// Y como es un Array, la función map SI serviria
paragraphs.map((p) => (p.style.color = "green"));

// El problema con Spread Operator es que NO se soporta 100% en todos los navegadores (EN 2018)

// CON ARRAY.FROM

// Convertimos el nodeList en un Array
const paragraphsArray = Array.from(document.querySelectorAll(".paragraph"));

// Y como es un Array, la función SI serviria
paragraphs.map((p) => (p.style.color = "blue"));
```

Siempre que trabajemos con QuerySelectorAll, recordemos convertirlo en Array si lo queremos tratar como tal. Que la MAYORIA DE VECES se debe usar como un Array. (Es el uso mas común)

# 25. DOM - Modificar atributos y clases

## Atributos

-   Si queremos definir un atributo a un elemento utilizamos 'setAttribute'

-   Si queremos obtener el valor de un atributo de un elemento utilizamos 'getAttribute'

```js
// Get Attribute
// Para obtener el valor del atributo de un elemento, como parametro pasamos el atributo que queremos consultar
console.log(name.getAttributte("type"));

// Set Attribute
// Para modificar o declarar el valor del atributo de un elemento, como parametro pasamos el atributo que queremos modificar y el valor que le vamos a dar.
name.setAttribute("type", "number");
```

## Clases

-   Si queremos agregar clases al elemento utilizamos 'classList.add' y podemos añadir todas las que queramos

-   Si queremos eliminar clases del elemento utilizamos 'classList.remove' y podemos eliminar todas las que queramos

-   Si queremos saber si tiene la clase o no utilizamos 'classList.contains' que devuelve 'true or false'

-   Si queremos sustituir una clase por otra, utilizamos 'classList.replace'. Recibe 2 parametros, la clase antigua, y la que la va a sustituir.

-   Si queremos que si NO tiene la clase la coloque, y SI la tiene se la quite, utilizamos 'classList.toggle'. **_SE USA MUCHO_**

**EJEMPLOS:**

```js
// 'classList.add'
// Añade clases, recibe como parametro una o mas clases que queramos añadir
title.classList.add("main-title");
title.classList.add("second-title", "other-title");

// 'classList.remove'
// Elimina clases, recibe como parametro una o mas clases que queramos eliminar. (Si colocamos una clase que no tiene no pasa nada)
title.classList.remove("main-title");
title.classList.remove("second-title", "third-title");

// 'classList.contains'
// Comprueba si esa clase existe en el elemento (true or false)
if (title.classList.contains("title")) console.log("Tiene la clase title");
else console.log("No tiene la clase title");

// 'classList.replace'
// Reemplaza una clase por otra, recibe como parametros la clase antigua y la clase que la va a reemplazar
title.classList.replace("title", "title-new");

// ClassList.toggle no lo veremos en esta CLASE
```

## Atributos Directos

Todos los atributos de la etiqueta que tengan un valor simple (Que no sean arrays o nodeList && Que no desplieguen varios elementos) pueden ser llamados de forma **DIRECTA**

A los que mas se suele acceder es al id, innerHtml, value, textContent, entre otros elementos.

**NOTA: El innerText NO es un estandar, se creo para internet explorer y CREO que ya no se usa**

```js
const title = document.getElementById("title");
const name = document.getElementById("name");

// Accedemos directamente al id
console.log(title.id);

// Accedemos directamente al innerHTML
// (InnerHTML: Recoge las etiquetas HTML del elemento y es diferente al 'textContent')
console.log(title.innerHTML);

// Accedemos directamente al value
console.log(name.value);
// Cuando queremos validar los campos de un formulario lo hacemos con el 'value'

// Accedemos a la longitud de lo que esta escrito
// Es necesario el value de lo contrario no nos serviria
console.log(name.value.length);
```

# 26. Eventos I - Eventos de ratón y teclado

## Introducción

Un evento es cualquier cosa que sucede en nuestro documento.(Los eventos no siempre son ejecutados por el usuario)

Hay muchos eventos que se disparan, sin que el usuario tenga que intervenir:

-   Cuando el contenido se ha leido
-   Cuando el contenido se ha cargado (Los recursos y todo)
-   Que el usuario mueva el ratón
-   Que el usuario pulse una tecla
-   Que la ventana se cierre
-   ETC...

Todos estos son ejemplos de eventos, y existen muchisimos mas que iremos abarcando

Hace unos años se llamaban los eventos desde HTML de esta forma

```html
<p onclick="saludo()">Soy un párrafo</p>
```

Esto es algo que a dia de hoy ya no se hace y que no es recomendable hacer por varias razones en especial porque estamos mezclando JS con HTML.

**NOTA: Hay sintaxis muy parecidas que utilizan Frameworks como Angular, en los que en este caso si estaria correcto utilizarla, EJEMPLO**

```html
<!-- Sintaxis de Angular, esto si es correcto -->
<p (click)="saludo()">Soy un párrafo</p>
```

Mientras que trabajemos en codigo puro, lo ideal es no mezclar lenguajes.

## La forma correcta

Para añadir un evento de la forma correcta lo haremos unicamente desde JS y tendra esta sintaxis.

```js
// Sintaxis
Element.addEventListener("event", callback);

// Ejemplo de click
loginBtn.addEventListener("click", () => {
    //write function
});
```

**NOTA: Si no conocemos algún evento o nos hace falta averiguar podemos ir a la documentación de mozilla developer**

## Observadores de mutación

**Resumen rapido:** Trabajan como **React** con el virtual DOM, react lo que hace es construir una copia virtual del DOM.

Cuando trabajamos con react interactuamos sobre el virtual DOM. El esta comparando y cuando hay un cambio en el virtual DOM, analiza el DOM y en el punto donde hay el cambio, cambia solo ese fragmento de codigo

Volviendo a los **OBSERVADORES DE MUTACIÓN** estos hacen algo parecido, observan el DOM y cuando existe un cambio nos avisan (que se ha añadido un nodo o se ha eliminado, ETC...)

## Eventos en practica

### Eventos de ratón

-   **click:** Cuando pulsamos el botón izquierdo del ratón

```js
// Creamos un evento click
button.addEventListener("click", () => {
    console.log("pulsamos click");
});
```

-   **dbclick:** Cuando pulsamos dos veces seguidas el botón izquierdo del ratón

```js
// Creamos un evento click
button.addEventListener("dbclick", () => {
    console.log("pulsamos doble click");
});
```

-   **mouseenter:** cuando entramos en la zona que tiene el evento (Como lo que hacemos con HOVER en CSS)

```js
// Creamos un evento mouseenter
box.addEventListener("mouseenter", () => {
    // Le cambiamos la clase 'red' por la clase 'green' cuando el mouse este dentro del 'box'
    box.classList.replace("red", "green");
    // Si no le configuramos 'mouseleave' la clase no se modificara asi salgamos de la caja
});
```

-   **mouseleave:** cuando salimos de la zona que tiene el evento (Como lo que hacemos con HOVER en CSS)

```js
// Creamos un evento mouseleave
box.addEventListener("mouseenter", () => {
    // Le cambiamos la clase 'green' por la clase 'red' cuando el mouse salga del 'box'
    box.classList.replace("green", "red");
});
```

-   **mousedown:** Cuando pulsamos el boton izquierdo del ratón

```js
// Creamos el evento mousedown
box.addEventListener('mousedown' ()=>{
    console.log('Has pulsado en la caja');
})
```

-   **mouseup:** Cuando soltamos el boton izquierdo del ratón

```js
// Creamos el evento mouseup
box.addEventListener('mouseup' ()=>{
    console.log('Has soltado el botón izquierdo en la caja');
})
```

**NOTA: mouseDown y mouseUp se usan en casos especificos, ejemplo cuando hacemos algo de arrastrar elementos, en esos casos es mejor usarlos en vez de click**

-   **mousemove:** Cuando movemos el ratón en el elemento al que le pongamos el evento

```js
// Creamos el evento mousemove
box.addEventListener('mousemove' ()=>{
    console.log('Has movido el mouse dentro de la caja');
})
```

### Eventos de Teclado

-   **keydown:** Cuando pulsamos una tecla

```js
// Creamos el evento keydown
box.addEventListener('keydown' ()=>{
    console.log('Has pulsado una tecla');
})
```

-   **keyup:** Cuando soltamos una tecla

```js
// Creamos el evento keyup
box.addEventListener('keyup' ()=>{
    console.log('Has soltado una tecla');
})
```

-   **keypress:** Cuando pulsamos una tecla y no la soltamos

```js
// Creamos el evento keypress
box.addEventListener('keypress' ()=>{
    console.log('Estas pulsando una tecla');
})
```

La idea de hacer estos eventos es SABER que tecla hemos PULSADO, el cual lo realizamos con el OBJETO EVENTO, que veremos la proxima clase.

# 27. Eventos II - Objeto Evento

El 99% de las veces que trabajemos con eventos usaremos el **objeto evento**. Este objeto consiste en darnos información del Evento.

El objeto evento existe siempre y cuando haya un evento, este nos da mucha información y nos abre un abanico de opciones como:

-   Saber la información del evento
-   Saber en que parte se da click
-   Saber que tecla se esta pulsando
-   **TARGET** es de lo mas usado

La mejor opción de trabajar con este objeto es enviarlo como parametro en el mismo evento `(e)`

```js
// Pasamos el objeto evento como parametro, y podemos hacer lo queramos con ese parametro.
input.addEventListener("keyup", (e) => {
    // Imprimimos el objeto (e) evento
    console.log(e);
});

// Si queremos sacar información mas especifica tambien lo podemos hacer no hay limite. podemos hacer lo queramos con ese parametro.
input.addEventListener("keyup", (e) => {
    // Imprimimos el id del objeto que se oprimio
    console.log(e.explicitOriginalTarget.attributes[0].nodeValue);
});
```

**ADICIONAL (Objeto global window)**

```js
// Window es el objeto global, por lo que podemos omitirlo en varios casos como:

addEventListener("click", (e) => {
    // Esto es lo mismo que poner window.addEventListener
    alert("Esto es lo mismo que poner window.alert");
});
```

**NOTA: Cuando trabajamos con una API nos enfrentamos a lo mismo que con un evento, esta nos devuelve x información y no sabemos que información, pero podemos obtenerla de esta misma manera**

## Target

Lo mas importante del objeto evento es recordar `target`, este hace referencia al punto de donde se origina el evento. POR EJEMPLO, el botón o la caja o lo que sea que se oprimio, target nos devuelve toda la INFORMACIÓN.

## Delegación de eventos (IMPORTANTE)

Si tenemos muchos elementos que requieren el mismo evento, la forma mas recomendada seria por la delegación de eventos. (Se podria hacer un bucle y darle el evento a cada uno, pero esto consume MUCHISIMOS RECURSOS)

La **delegación de eventos** consta en darle el evento de escucha al contenedor padre de estos elementos, y localizar en que elemento hijo fue que se hizo click.

```js
// Contenedor de los item de la galeria (Elemento padre)
const gallery = document.getElementById("gallery");

// Le damos la escucha al elemento padre
gallery.addEventListener("click", (e) => {
    // Nos muestra a que item de la galeria le damos click (Conseguimos lo mismo que si le dieramos evento 1x1)
    console.log(e.target.textContent);
});
```

Esto se puede aplicar a todo tipo de proyecto, por ejemplo en un formulario con muchos campos, añadirle a cada campo un evento, es un gasto de recursos muy muy grande.

## Evitar el reinicio de la pagina con forms

Normalmente nosotros no enviamos el form directamente, escuchamos el submit y ejecutamos.

### Metodo Prevent.default

Es el metodo que tienen los eventos para decirle que no queremos ejecutar el evento por defecto, esto funciona con todos los elementos HTML

Sin embargo, se suele utilizar es en **formularios**, porque normalmente no queremos que el form se envie cuando trabajamos de forma asincrona. o algunas veces no queremos que pase cierta cosa hasta que suceda algo mas

```js
// Botón de envio de formulario
form.addEventListener("submit", (e) => {
    // Conseguimos que el botón no haga lo que tiene predefinico hacer, en este caso enviar el form
    e.preventDefault();
});

// Esto funciona con todos los elementos html

// Enlace a pagina
link.addEventListener("click", (e) => {
    // Evita que vayamos al enlace que le definimos, no haria nada
    preventDefault();
});
```

## Los eventos, se pueden escuchar o forzar.

Nosotros podemos forzar que un evento se dispare, se debe pasar el evento como función

```js
// el elemento y el evento que queremos forzar(Se pasa como función)
button.click();
// Forzamos click en el botón
```

Esto nos puede servir muchas veces, cuando necesitamos que se dispare un evento, pero sin esperar la interacción del usuario.

# 28. DOM - Javascript crear e insertar elementos I

Vamos a aprender a como crear e insertar elementos en el DOM de la primer forma, hay bastantes mas que veremos en las siguientes clases.

## Crear un elemento

Cuando queremos crear un elemento es lo mismo que crear una etiqueta en el DOCUMENTO, por eso el metodo `createElement` debe ir siempre con `document` asi: `document.createElement` NO puede ir con otro que no sea document.

```js
// Creamos un elemento de lista (createElement)
const itemList = document.createElement("LI");
// Le agregamos contenido al elemento creado
itemList.textContent = "Lunes";
```

**NOTA: Hasta aquí ya creamos el elemento, PERO no lo hemos insertado en el DOM**

## Insertar elemento al DOM

Para añadir un elemento a la lista la primera forma es con esta sintaxis `parent.appendChild(element)`, SIEMPRE que queramos añadir un elemento ese elemento debe ser HIJO de un alguien, incluso del body.

```js
// daysList es una lista vacia, agregamos el elemento que creamos antes
daysList.appendChild(itemList);
```

## InnerHTML

InnerHTML la utilizamos si nosotros necesitamos insertar etiquetas HTML dentro de otra etiqueta y que el navegador las interprete como etiquetas y no como texto

**EJEMPLO**

Queremos insertar un `span` dentro de una etiqueta `h1`. Si utilizamos `textContent` para hacerlo el `span` se interpretaria como texto y no como etiqueta, en este caso necesitariamos utilizar `innerHTML`

```js
// De esta forma nos interpreta la etiqueta span como texto y nos apareceria tal cual
title.textContent = "DOM - <span>Crear e insertar elementos</span>";

// De esta forma el span se tomaria como etiqueta y no apareceria como texto en el H1
title.innerHTML = "DOM - <span>Crear e insertar elementos</span>";
```

## Insertar un array en el DOM (Lista)

Tenemos un array con los dias de la semana, y queremos agregarlo a una lista `ul` que tenemos en nuestro HTML.

**BASE**

```js
// Lista vacia en el HTML
const daysList = document.getElementById("daysList");

// Select vacio en el HTML
const daysSelect = document.getElementById("daysSelect");

// Array con dias de la semana
const days = [
    "Lunes",
    "Martes",
    "Miercoles",
    "Jueves",
    "Viernes",
    "Sabado",
    "Domingo",
];
```

**EJEMPLO**

-   Primero lo vamos a realizar con `innerHTML` aunque esta NO es la mejor opción.

```js
for (const day of days) {
    // Recorremos el array y agregamos dia a dia con innerHTML
    /* Colocamos (+=) para que se agregue y no se sobreescriba */
    daysList.innerHTML += `<li>${day}</li>`;
}
```

**El problema de esta forma es que a CADA vuelta de bucle le estamos inyetando codigo HTML en el DOM, cada vez que nosotros agregamos un elemento el DOM se redibuja completamente y es un GRAN GASTO DE RECURSOS**

## createDocumentFragment

Debido al problema anterior se creo el `createDocumentFragmet()` para evitar que el navegador se sobre cargara con este tipo de operaciones.

Basicamente un fragmento de codigo es una variable donde nosotros vamos a escribir todo el HTML que queremos inyectar en el documento, y despues de tenerlo todo lo inyectamos TODO el codigo de golpe y de esta forma ahorramos MUCHISIMOS recursos al navegador

```js
const fragment = document.createDocumentFragment();

for (const day of days) {
    // Creamos un elemento de lista (createElement)
    const itemList = document.createElement("LI");
    // Le agregamos contenido al elemento creado
    itemList.textContent = day;

    // Se lo agregamos al FRAGMENTO que creamos anteriormente
    fragment.appendChild(itemList);
}

// Aca solo le agregamos a la lista nuestro fragmento y hacemos una UNICA inyección de codigo al DOM
daysList.appendChild(fragment);
```

## Rellenar un SELECT desde JS

Para agregar opciones a un select es algo muy parecido, aunque tenemos que modificar el atributo `value` del select al igual que el `textContent`.

```js
for (const day of days) {
    // Creamos una opción de select (createElement)
    const selectItem = document.createElement("OPTION");
    // Le agregamos contenido al elemento creado
    selectItem.textContent = day;
    selectItem.setAttribute = ("value", day.toLowerCase);

    // Se lo agregamos al FRAGMENTO que creamos anteriormente para no sobrecargar el DOM
    fragment.appendChild(selectItem);
}

// Aca solo le agregamos al select nuestro fragmento y hacemos una UNICA inyección de codigo al DOM
daysSelect.appendChild(fragment);
```

# 29. Traversing

El **DOM traversing** se le llama a la practica de situarnos en un NODO y saber movernos hacia arriba y hacia abajo por el DOM.

Los metodos para subir y bajar por el DOM los dividiremos en Padres, Hijos y Hermanos.

## Metodos Padre

```js
// Este va a ser nuestro objeto de referencia para movernos por el DOM
const parent = document.getElementById("parent");
```

-   `parentNode` : Devuelve el nodo padre (que puede NO ser un elemento)

-   `parentElement` : Devuelve el nodo elemento padre

```js
// Nos imprime el elemento PADRE del elemento que referenciamos
// (Si no tuvieramos 'nada' el padre seria body)
console.log(parent.parentNode);
console.log(parent.parentElement);
```

La supuesta diferencia es que `parentNode` puede que devuelva un padre que NO sea un elemento, pero según la experiencia de dorian NO hay ningún caso que esto se de.

**NOTA: Los nodos de tipo document y documentFragment nunca van a tener un elemento padre, parentNode devolvera siempre null.**

## Metodos Hijos

Los nodos hijos son los que descienden de un padre.

```js
// Este va a ser nuestro objeto de referencia para movernos por el DOM
const parent = document.getElementById("parent");
```

Metodos:

-   `childNodes`: Devuelve todos los nodos hijos.

-   `children`: Devuelve todos los nodos ELEMENTOS hijos.

-   `firstChild`: Devuelve el primer nodo hijo.

-   `firstElementChild`: Devuelve el primer nodo ELEMENTO hijo

-   `lastChild`: Devuelve el último nodo hijo

-   `lastElementChild`: Devuelve el último nodo ELEMENTO hijo

-   `hasChildNodes()`: Devuelve true si el nodo tiene hijos y false sino tiene

**RECOMENDACIÓN: Siempre que intentemos localizar etiquetas, usemos los metodos que localizan nodos elementos para que no hayan problemas**

```js
// Nos devuelve TODOS los nodos HIJOS, algunos como saltos de linea y eso que no nos son utiles.
console.log(parent.childNodes);

// Nos devuelve TODOS los nodos ELEMENTOS hijos, es decir las etiquetas que son hijas
// Es la que se suele utilizar
console.log(parent.children);

// Nos devuelve el primer nodo hijo, que es normalmente un (salto de linea)
console.log(parent.firstChild);

// Nos devuelve el primer nodo ELEMENTO hijo, como la primera etiqueta hija
console.log(parent.firstElementChild);

// Nos devuelve el ultimo nodo hijo, que es normalmente un (salto de linea)
console.log(parent.lastChild);

// Nos devuelve el ultimo nodo ELEMENTO hijo, como la ultima etiqueta hija
console.log(parent.lastElementChild);

// Nos devuelve true or false si el nodo tiene o no hijos respectivamente
console.log(parent.hasChildNodes());
```

## Metodos Hermanos

```js
// Este va a ser nuestro objeto de referencia para movernos por el DOM
const parent = document.getElementById("parent");
```

-   `nextSibling`: Devuelve el siguiente nodo hermano

-   `nextElementSibling`: Devuelve el siguiente nodo ELEMENTO hermano

-   `previousSibling`: Devuelve el anterios nodo hermano

-   `previousElementSibling`: Devuelve el anterior nodo ELEMENTO hermano

```js
// Nos devuelve el siguiente nodo hermano (Normalmente un salto de linea)
console.log(parent.nextSibling);

// Nos devuelve el siguiente nodo ELEMENTO hermano, como la etiqueta siguiente
console.log(parent.nextElementSibling);

// Nos devuelve el anterior nodo hermano (Normalmente un salto de linea)
console.log(parent.previousSibling);

// Nos devuelve el anterior nodo ELEMENTO hermano, como la etiqueta anterior
console.log(parent.nextElementSibling);
```

## Cercano

-   `closest(selector)`: Selecciona el nodo más cercano que cumpla con el selector, AUN ES EXPERIMENTAL. No es un estandar por lo que no veremos mas por el momento.

# 30. DOM - Insertar, clonar y borrar elementos

Las practicas las hacemos con una lista porque es de las formas mas entendibles, pero TODO ESTO se puede hacer con cualquier tipo del elemento del DOM.

## Insertar elementos II

1. Agregar un elemento de la forma principal

```js
// APPENDCHILD
// De esta forma se coloca SIEMPRE de ULTIMO LUGAR
list.appendChild(newElement);
```

2. Metodos de conveniencia de manipulación del DOM. Agregar un elemento utilizando un elemento de referencia

-   `parent.insertBefore(newElement, referenceElement)`: Insertar un elemento ANTES del elemento de referencia.(Tiene soporte TOTAL)

```js
// INSERT BEFORE
// Insertarlo antes de un elemento especifico

// En este caso lo colocariamos ANTES del hijo 0, es decir de primeras
list.insertBefore(newElement, list.children[0]);
```

## Otros metodos para insertar elementos (Con soporte hasta en internet explorer)

Estos metodos tienen soporte TOTAL y requieren unas posiciones que vamos a ver a continuación.

### Positions (Posiciones)

-   `beforebegin`: Antes de que empiece (Hermano anterior del elemento)

-   `afterbegin`: Despues de que empiece (Primer hijo del elemento)

-   `beforeend`: Antes de que acabe (Ultimo hijo del elemento)

-   `afterend`: Despues de que acabe de que acabe (Hermano siguiente del elemento)

### Metodos para insertar elementos

-   `parent.insertAdjacentElement(position, element)`: Inserta un elemento dependiendo la posición que le pasemos

```js
// Insert Adjacent Element
// Inserta un elemento dependiendo la posición que le pasemos

// En este caso lo inserta como hermano anterior de la lista
list.insertAdjacentElement("beforebegin", newElement);

// En este caso lo inserta como primer hijo de la lista
list, insertAdjacentElement("afterbegin", newElement);

// En este caso lo inserta como ultimo hijo de la lista
list, insertAdjacentElement("beforeend", newElement);

// En este caso lo inserta como hermano siguiente de la lista
list, insertAdjacentElement("beforeend", newElement);
```

**NOTA: Tener muy en cuenta la referencia que le pasemos, porque podemos desbordar y generar error**

-   `parent.insertAdjacentHTML(position, <li>Etiqueta HTML</li>)`: Este es muy poco usado, en vez de pasarle un elemento, le pasamos directamente la etiqueta que queramos crear (Las posiciones funcionan igual)

-   `parent.insertAdjacentText(position, texto)`: Este tambien es muy poco habitual, sencillamente estamos introduciento un texto (Las posiciones funcionan igual)

## Reemplazar un elemento hijo con otro

-   `parent.replaceChild(newChild, oldChild)`: Reemplaza un hijo por otro.

```js
// Reemplazando elementos hijos
// Reemplazamos el hijo de la posición 1 por el nuevo elemento
list.replaceChild(newElement, list.children[1]);
```

## Otros metodos para insertar elemento (Con soporte casi absoluto)

Estos metodos que veremos hacen lo mismo que los anteriores y con una sintaxis mas sencilla, tienen un soporte practicamente absoluto y en el unico navegador que no se soporta es en **Internet Explorer** que a dia de hoy ya no existe, por lo que es muy recomendable usar estos metodos que se denominan **DOM manipulation convenience methods**

**Metodor para insertar**

-   `parent.before()`: Antes de que empiece (hermano anterior)
-   `parent.prepend()`: Despues de que empiece (primer hijo)
-   `parent.append()`: Antes de que termine (Ultimo hijo)
-   `parent.after()`: Despues de que termine (Hermano siguiente)

```js
// Lo insertamos como hermano de la lista
list.before(newElement);

// Lo insertamos como primer hijo de la lista
list.prepend(newElement);

// Lo insertamos como ultimo hijo de la lista
list.append(newElement);

// Lo insertamos como hermano siguiente de la lista
list.after(newElement);
```

**Metodor para reemplazar**

-   `child.replaceWith(newChild)`

```js
// Reemplazamos un hijo de la lista por el nuevo elemento
list.children[0].replaceWith(newElement);
```

## Clonar elementos

Para clonar elementos tenemos estos metodos

-   `element.cloneNode(true||false)`: Clona el nodo. Si le pasamos `true` clona TODO el elemento con los hijo, si le pasamos `false` clona solo el elemento SIN los hijos

```js
// Creamos una copia de la lista, CON los elementos hijos
list.after(list.cloneNode(true));

// Creamos una copia de la lista, SIN los elementos hijos (Solo clonamos la lista)
list.after(list.cloneNode(false));
```

Esto se suele hacer cuando tenemos un elemento que se va a repetir en varias ocaciones y **NO TIENE UN ID**

## Eliminar elementos

Para eliminar elementos tenemos los siguientes metodos

-   `element.remove()`: Elimina el nodo del DOM
-   `element.removeChild(child)`: Elimina el nodo hijo del DOM

```js
// Eliminamos la lista
list.remove();

// Eliminamos 1 hijo de la lista
list.removeChild(list.children[0]);
```

# 31. Objetos Nativos y timers

## Objeto window

Es el objeto GLOBAL, de él descienden todos los objetos.

Siempre que no pongamos nada antes, el navegador va a entender que nos estamos refiriendo a `window`.

-   `alert()`
-   `prompt()`
-   `confirm()`

Esto es igual que tener window antes, por ejemplo `window.document`, `window.alert()`, etc...

**Evento de carga de la pagina**

```js
// Dentro le colocamos lo que queremos que pase cuando carga la pagina
addEventListener("load", (e) => {
    console.log(e);
});
```

## Objeto console

Es el objeto que contiene la consola del navegador

-   `console.log()`: Imprime en la consola lo que queramos

-   `console.dir()`: Imprime tambien en consola, sin embargo hay una pequeña diferencia y veces donde `console.dir` imprime mas información que `console.log`.

-   `console.error()`: Podemos imprimir mensajes de ERROR en la consola

-   `console.table()`: La visualización es en forma de 'tabla' y es MUCHO mas facil de verlo, por si lo necesitamos

## Objeto Location

Es el objeto que contiene la barra de direcciones

Algunos metodos de este objeto son:

-   `location.href`: Nos devuelve la URL y tambien nos sirve para cambiar el valor de la URL (Es una forma de redirigir a paginas a traves de JS)

-   `location.protocol`: Nos devuelve el protocolo de la pagina (http || https || ftp)

-   `location.host`: Nos devuelve el dominio principal que estemos viendo. No nos devuelve rutas ni nada, solo el dominio, lo que va antes del `/`

-   `location.pathname`: Nos devuelve unicamente la ruta en la que estamos, NO el dominio sino lo que va DESPUES del `/`

-   `location.hash`: Es una forma de pasar parametros entre paginas, podemos utilizarlo para tener 1 solo HTML y en función del `hash` que pasemos cargar una información u otra

-   `location.reload()`: Recarga la pagina

Tiene muchos otros metodos que podemos consultar

## Objeto History

Este objeto trabaja con el historial de la pestaña que estamos navegando

Estos son todos los metodos de este objeto:

-   `history.back()`: Para ir atras, es el botón atras del navegador

-   `history.forward()`: Para ir adelante, es el botón adelante del navegador

-   `history.go(n | -n)`: Podemos navegar a traves del historial X paginas hacia adelante o X paginas hacia atras

-   `history.length`: Sabemos cuantas paginas tiene el historial en esta pestaña

## Objeto Date

Este objeto trabaja con fechas, tiene una peculiaridad y es que para utilizarlo necesitamos INSTANCIARLO (Crearlo).

Tiene muchisimos metodos aunque afortunadamente son bastante intuitivos y funciona practicamente igual que el objeto date de TODOS los lenguajes de programación

```js
const date = new Date();

// Obtenemos el dia de hoy (Empieza a contar desde 0, donde 0 es domingo y 6 es Sabado)
console.log(date.getDay);

// Obtenemos el mes actual (Empieza a contar desde 0, donde 0 es enero y 11 es Diciembre)
console.log(date.getMonth);

// Obtenemos el dia del mes (15,16,20,etc...)
console.log(date.getDate);

// Obtenemos toda la fecha
console.log(date);
```

Hay muchos metodos mas que podemos consultar en caso de llegarlos a necesitar

## Timers

### Timeout 

Podemos establecer el 'delay' o el tiempo de espera de una función antes de su ejecución. La ejecución se lee y pasados X segundos se ejecuta.

-   `setTimeout(()=>{code}, delay-in-miliseconds)`: Hace que se ejecute la función despues del delay. Si lo referenciamos mediante una variable/constante podemos pararlo con `clearTimeout(reference)`

```js
const saludar = () => {
    console.log("hola");
};

// Cuando hagamos click en el botón se va a tomar 3 segundos (3000ms) para ejecutar la función saludar
button.addEventListener("click", () => {
    // Cuando vamos a usar una función externa, no es necesario colocar '()=>'
    setTimeout(saludar, 3000);

    // Si la función la escribieramos ahí mismo si seria como funcion flecha
    setTimeout(() => {
        console.log("Adios");
    }, 3000);
});
```

Si queremos detener la ejecución de la función lo podemos hacer con `clearTimeout(reference)`

```js
// Es necesario tener la funcion referenciada en una variable o constante
const timeOut = setTimeout(() => {
    console.log("adios");
}, 3000);

// Cuando le demos click al función la funcion se detendra
button.addEventListener("click", () => {
    // Aca llamamos el metodo y le pasamos la función que queremos detener
    clearTimeout(timeOut);
});
```
### Interval 

Con interval la función no se ejecuta una sola vez, se ejecuta todas las veces cada X segundos

- `setInterval(()=>{code}, delay-in-miliseconds)`: Hace que se ejecute la función cada delay milisegundos, Si lo referenciamos mediante una variable/constante podemos pararlo con `clearInterval(referencia)`

```js
// Cada 3 segundos se ejecutara la función saludar
const interval = setInterval(saludar, 3000);

// Cuando le demos click al botón se detendra el interval
button.addEventListener('click',()=>{
    // Lo usamos para frenar el interval (El interval debe estar referenciado)
    clearInterval(interval);
})
```
