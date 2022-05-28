# 1. Historia de JavaScript
 * Es un lenguaje de programación que sirve para la web, y el unico que puede interpretar un navegador
* Antes del 2009 no era muy importante y se burlaban de el lenguaje
* Actualmente con node.js podemos hacer tambie back-end
* En el 2015 salio ECMAScript 6 que revoluciono el lenguaje 

## Tecnologias descendientes de JavaScript MAS IMPORTANTES
* Ajax => Obtener información del server
* jQuery => Ya no es necesario y es pesada 
* nodeJS => Permite ejecutar JS desde un server
* JSON => Sustituye el XML 

## Frameworks MAS IMPORTANTES
* Angular
* React
* VueJs

# 2. Sintaxis y tipos de datos
## Sintaxis (Condiciones)
* Es case sensitive
* Es de tipado débil o dinamico
* Las sentencias finalizan con ;
* Los bloques finalizan con } y se puede colocar despues un ; (Opcional)
## Variables y constantes 
* Es lo mismo que en otro lenguaje de programación
* Para declarar una variable se usa la palabra reservada "let", NO es RECOMENDABLE usar "var" porque genera problemas
* Para declarar una constante se usa la palabra reservada "const"
## Scope o Ambito
* Es la zona (el sitio) donde existe nuestra variable o cosntante - Es decir dentro de un bloque etc...

# 3. Operadores en JavaScript
* Son los operadores de toda la vida 
* "a++" Primero devuelve la variable y luego la incrementa
* "++a" Primero incrementa la variable y luego la devuelve

# 4. Metodos y propiedades de los String
* Los metodos es todo aquello que la cadena puede hacer
* Las propiedades son la caracteristicas de las cadenas

## Template String (format string)
```js
console.log(`Hola ${nombre} ${apellido}. Tienes ${edad} años.`);
```
# 5. Objeto Math
Es un objeto que se utiliza para operaciones matematicas mas especificas (Tambien utiliza la nomenclatura del ".")

## Metodos 
Tiene muchos metodos pero los principales son:
* Math.abs(x) => Devuelve valor absoluto de x
* Math.ceil(x)=> Redondea hacia abajo
* Math.floor(x) => Redondea hacia arriba
* Math.pow(x,y) => Devuelve la potencia de x elevado a y
* Math.random() => Devuelve un numero aleatorio entre 1 y 0
* Math.round(x) => Redondea al entero mas cercano
* Math.sign(x) => Devuelve el signo de x, si es negativo o positivo

```js
console.log(Math.abs(-8));
console.log(Math.ceil(8.7));
console.log(Math.floor(8.7));
console.log(Math.pow(3,2));
console.log(Math.random());
console.log(Math.round(3.5));
console.log(Math.sign(-3));
```
## Hacer un numero aleatorio entre 0 y un numero mayor a 1 (que sea entero)
```js
// Numero aleatorio entero entre 0 e indefinido
console.log(Math.random()*100);
// Numero aleatorio definiendo limites entre maximo y minimo
console.log(Math.round(Math.random() * (10 - 5)+5));
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
} else if(b>=a && b>=c) {
    if (a >= c) {
      console.log(b, a, c);
    } else {
      console.log(b, c, a);
    }
} else if(c>=a && c>=b){
    if (a >= b) {
        console.log(c, a, b);
      } else {
        console.log(c, b, a);
      }
}

```
# 8. Condicional Switch
Se utiliza para elegir un camino de varios preestablecidos. Tenemos 3 tipos principales:
* Sintaxis Simple
    * Ejecuta un codigo diferente dependiendo del caso
* Sintaxis multiple
    * Puede ejecutar un mismo codigo en una serie de casos 
    ```js
        switch (num) {
            case 1:
            case 2:
            case 2:
                // Codigo para esos 3 casos
                break;
        }
    ```
* Sintaxis Multiple encadenada (No nos explica porque no se usa mucho )

# 9. Operador Ternario
* Puede tener una sentencia o varias 
    * (condición)? true:false
    ```js
    let num = 0;

    // Operador ternario
    (num % 2 == 0) ? console.log(`${num} es par`): console.log(`${num} es impar`);
    ```
# 10. Arrays
* En JavaScript nos permiten almacenar VARIOS TIPOS de datos en un mismo Array, sin embargo hacer esto NO ES RECOMENDABLE
* Se declaran con llaves cuadradas o corchetes []
* Pueden añadirse o eliminarse elementos (Como una lista)

# 11. Arrays II
* length => longitud del array
* push => Añade elementos al final y devuelve la longitud(es pocional usarla)
* unshift => Añade elementos al principio del array y devuelve su longitud
* reverse => Le da la vuelta al array
* splice => elimina desde posiciones

# 12. Bucle While - Do-While 
Exactamente lo mismo de siempre
# 13. Bucle For 
* La i de variable viene de INCREMENTO
* De resto es todo igual a lo que conocemos
