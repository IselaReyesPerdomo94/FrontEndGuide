# Front-End-Guide

Hola! Te doy la bienvenida al mundo del front end, enfocado en el desarrollo web.

En este repositorio encontrarás una lista de temas que te servirán para comenzar en el mundo del desarrollo.

Este proyecto esta en desarrollo por lo que espera ver cambios. 
Nota: utilizaré términos en inglés y en español todo el tiempo. La gran mayoría de la información y documentación esta disponible en inglés y mis fuentes generalmente será en inglés.

![cat-coding](https://hostrider.com/images/tw.png)

## Desarrollo web  (FRONT END)

Una de las carreras mas nobles (en mi opinión) para entrar al mundo tech, debido a que hay una alta demanda de programadores en esta área, el feedback es casi inmediato (tanto si lo estas haciendo bien como si lo estas haciendo mal).


Los elementos principales que necesitas para comenzar tu carrera como desarrollador web son:
- [HTML](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
  > HyperText Markup Language, es el codigo que se utiliza para estructurar una página web y su contenido. HTML consiste en una serie de elementos que designan y agrupan contenido. 
  Es el esqueleto de la página web, si lo vieramos como un edificio, HTML serían las paredes, cimientos, vigas, que designan espacios.
- [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
  > Cascading Style Sheets es un lenguage de hoja de estilos que se utiliza para describir la presentación de un documento escrito en HTML o XML. CSS describe como los elementos van a ser renderizados en la pantalla. Vaya que aqui se agrega el *estilo* colores, tipografia, ordenamiento e incluso animaciones. 
  Reutilizando la analogía del edificio, CSS sería la pintura, los acabados, el color del piso, la iluminación.
- [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
  > Es un lenguage de programación interpretado, que es el único que funciona en los navegadores de forma nativa. Es decir, se dice interpretado porque no necesitas compilarlo. Este se utiliza para darle interactividad a un sitio web. En la analogía del edificio, JavaScript sería el que te permitiría prender la luz con un switch, usar un elevador, abrir la llave del agua y que salga agua del grifo. JavaScript es utilizado para provocar algo al escuchar un evento.


## JavaScript conceptos básicos
1. [Tipos de datos](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#javascript_types):
  - Valores primitivos
    - boolean: Representan un valor lógico el cual puede ser: `true` or `false`, verdadero o falso. 
    ```js 
    const isJSAProgrammingLanguage = true;
    ```
    - null: Solo puede ser un valor, que es nulo. 
    - undefined: Significa que una variable no esta definida
    - number: Representa un número, positivos: `1`, flotantes: `1.44`, negativos: `-0.34`
    - NaN: `Not a Number` este valor te lo encuentras cuando el resultado de una operación aritmetica no puede ser expresado como un número.
    ```javascript
    const canNotBeTransformed = parseInt('student'); //NaN
    ```
    - string: Cadenas de texto, ejemplo: 'student', 'javascript'.
  - Objetos
    - Object: Colección de propiedades, se considera un valor complejo, su cuerpo es formado por `brakets: {}`, `keys` y `value`, ejemplo:
    ```js
      const student = {
        age: 25, // age es una key, 25 es value
        name: 'Pepito',
        lastName: 'Pérez',
      }
    ```
      Para obtener sus valores podemos hacerlo de la siguiente manera:
      ```js
      student.age //25
      student['name'] // 'Pepito'
      ```
    - Array, tambien es un objeto, este se utiliza como una lista de elementos. Te permite guardar una colección de multiples elementos en una sola variable.
    ```js
    const words = ['student', 'car', 'salesman', 'blue'];
    // Una lista de palabras.
    ```
2. [Variables](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables)
  Se utilizan para guardar información.
  - const: Se utiliza para guardar valores constantes, debe ser inicializada al momento de declararla, para declarar una variable constante se necesita la palabra `const` un nombre, el operador que asigna `=` y un valor:
  ```javascript
  const car = 'auto'; // success
  const tu; // error
  car = 'carro'; // error
  // Note: Una constante no puede ser declarada sin valor.
  ```
  Puedes acceder a su valor siempre y cuando, la llames esten dentro del mismo scope
  ```js
  const printHello = () => {
    const greeting = 'Hello';
    console.log(greeting)
  }
  // imprime: 'Hello
  greeting // error, greeting fue declarada dentro de la funcion printHello, ese valor solo existe dentro de la función, no afuera
  ```
  - let: Se utiliza para declarar variables y guardar valores en las variables. Let si puede ser declarada sin asignarle un valor, tambien se puede reasignarle un valor.
  ```javascript
  let car = 'auto'; // success
  let tu; // success
  car = 'carro'; // success
  // Note: Una constante no puede ser declara sin valor.
  ```
  - var: En un inicio, era la única manera de declarar variables, var igualmente se utiliza para almacenar un valor, la diferencia entre var, `const` y `let`, es que `var` se puede declarar sin asignarle un valor (como `let`). Puedes acceder a su valor desde cualquier parte
  ```js
  const printHello = () => {
    var greeting = 'Hello';
    console.log(greeting)
  }
  // imprime: 'Hello
  greeting // 'Hello', greeting fue declarada dentro de la funcion printHello, var es afectada por el hoisting, que significa que la variable se mueve a la parte superior del código por lo que si puedes acceder a su valor, aunque haya sido declarada dentro de la función. 

  //Es como si hubiera pasado esto:
  var greeting = 'Hello';
  const printHello = () => {
    console.log(greeting)
  }
  // imprime: 'Hello
  greeting
  ```


3. [Operadores](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators):
  - binarios, unarios y ternarios.
    - binarios: se necesitan 2 operandos por ejemplo `3 + 4` el `3` y el `4` serían los operandos, y el `+` es el operador, en este caso una suma.
    - unarios: Solo se necesita 1 operando, por ejemplo `typeof 'student'` `typeof` es operador que significa "tipo de" y `student` es el operando, que simplemente es una cadena de texto. El resultado de `typeof 'student'` sería "string"
    - ternarios: Como su nombre lo indica, significa `3`, 3 operandos, es decir, 3 elementos necesarios para utilizar el operador, ejemplo: 
    ```JavaScript
    const age = 25; // edad de una persona
    const status = age >= 18 ? 'adult' : 'minor'; // si su edad es mayor o igual a 18 status sería 'adult' de lo contrario su valor seria 'minor';
    const canHaveDrivingLicence = status === 'adult'; // Esta es una evaluacion binaria, el valor de canHaveDrivingLicense sería, `true` si status es igual a 'adult'
    ``` 
  - [Asignamiento](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#assignment_operators)
    Asigna un valor al operante izquierdo con el valor pasado del lado derecho
    `const car = 'carro'`
      Tambien existe el asignamiento con suma, asignamiento con resta, con multiplicacion, división, residuos entre otros.
  - [Comparativos](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#comparison_operators): retorna verdadero o falso si el elemento de la izquierda comparados entre si, dependiendo de la evaluacion da true o false.
  ```js
  3 === 3// true
  ```
    `==` equal
    `!=`not equal
    `===` strict equal
    `!==` strict not equal
    `>` greater than
    `>=` greater than o equal
    `<` less than
    `<=` less than or equal
  - Aritmeticos: Operadores que toman valores numericos y retornar un valor numerico:
  ```js
    `+` suma 3 + 3 // 6
    `-` resta 3 -3 // 0
    `*` multiplicación 3 * 3 // 9
    `/` división 3 / 3 // 1
    `%` residuo 3 % 3 // 0 
    // El residuo o remainder es un operador binario que retorna lo que sobra cuando divides 2 numeros, ejemplo, 3 / 3 es igual a 1, no sobra ningun numero. 12 % 5, se traduciria a 12 entre 5, cabe 2 veces y sobran 2, entonces 12 % 4 = 2

    `++` Incremento 3++ // 4, toma el numero y suma 1
    `--` Decremento 3-- // 2, Toma el numero y resta 1
    `-` Negación unaria -3 // -3, Numero negativos
    `+` Incremento unario +3 // 3, Intenta convertir el operando en numero si no lo es ya.
    +true // 1
    `**` Exponente 2 ** 3// 8, calcula la base con el exponente, la base seria 2 y el exponente 3, es decir 2 * 2 * 2 = 8
```
  - Operadores lógicos: Usualmente utilizados con boleanos, aunque tambien pueden ser usados con numeros o strings o combinados.
![Operadores logicos](https://content.codecademy.com/practice/art-for-practice/new-pngs/Boolean-operators-dk.png)

4. [Condicionales](https://www.w3schools.com/js/js_if_else.asp)
- if: Para especificar que un bloque de codigo debe ser executado (se tiene que cumplir la condicion);
```js
const age = 33;
if(age > 18) {
  console.log('wow you are an adult')
}
```
- else: Para especificar que un bloque de codigo se execute si la condición anterior no se cumplió
```js
const age = 12;
if(age > 18) {
  console.log('wow you are an adult')
} else {
  console.log('you are just a child')
}
```
- else if: Para especificar una nueva condición, si la primera condición no se cumple
```js
const age = 85;
if(age > 18 && age < 60) {
  console.log('wow you are an adult')
} else if (age > 60 ) {
  console.log('wow, you are really old')
} else {
  console.log('you are just a child')
}
```
- ternario: Retorna un valor si la condición se cumple, si no retorna el segundo valor
```js
const age = 12;
age > 18 
  ? console.log('wow you are an adult') 
  : console.log('you are just a child')

```
- switch case: Especifica varias alternativas que se ejecuten dependiendo de la condición que se cumpla.
```js
const expr = 'Papayas';
switch (expr) {
  case 'Oranges':
    console.log('Oranges are $0.59 a dollars');
    break;
  case 'Mangoes':
  case 'Papayas':
    console.log('Mangoes and papayas are $2.79 a dollars');
    // expected output: "Mangoes and papayas are $2.79 a dollars"
    break;
  default:
    console.log(`Sorry, we are out of ${expr}.`);
}
```

Convenciones de código:
- cammelCase
- PascalCase
- snake_case

## Node
## Git 

## Github

## Metodo de trabajo agile
> Agile Methodology is a people-focused, results-focused approach to software development that respects our rapidly changing world. It’s centered around adaptive planning, self-organization, and short delivery times. It’s flexible, fast, and aims for continuous improvements in quality, using tools like Scrum and eXtreme Programming.

### Scrum

## Proyectos/Portafolio

## Librerias

## Frameworks

## Soft skills

## Entrevistas de trabajo