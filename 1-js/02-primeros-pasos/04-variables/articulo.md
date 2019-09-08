# Variables

La mayoría de las veces, una aplicación JavaScript necesita trabajar con información. Aquí hay dos ejemplos:
1. Una tienda en línea: la información puede incluir productos que se venden y un carrito de compras.
2. Una aplicación de chat: la información puede incluir usuarios, mensajes y mucho más.

Las variables se utilizan para almacenar esta información.

## Un variable

Un [variable](https://en.wikipedia.org/wiki/Variable_(computer_science)) es un "almacenamiento con nombre" para datos. Podemos usar variables para almacenar golosinas, visitantes y otros datos.

Para crear una variable en JavaScript, use la palabra clave `let`.

La siguiente declaración crea (en otras palabras: *declara* o *define*) una variable con el nombre "mensaje":

```js exemplo
let mensaje;
```

Ahora, podemos poner algunos datos en él usando el operador de asignación `=`:


```js exemplo
let mensaje;

*!*
mensaje = 'Hola'; // almacenar un tipo string
*/!*
```

La cadena ahora se guarda en el área de memoria asociada con la variable. Podemos acceder usando el nombre de la variable:

```js exemplo
let mensaje;
mensaje = 'Hola!';

*!*
alert(mensaje); // muestra el contenido variable
*/!*
```

Para ser conciso, podemos combinar la declaración de variables y la asignación en una sola línea:

```js exemplo
let mensaje = 'Hola!'; // define la variable y asigna el valor

alert(mensaje); // Hola!
```

También podemos declarar múltiples variables en una línea:

```js exemplo
let usuario = 'John', edad = 25, mensaje = 'Hola';
```

Eso puede parecer más corto, pero no lo recomendamos. En aras de una mejor legibilidad, utilice una sola línea por variable.

La variante multilínea es un poco más larga, pero más fácil de leer:

```js exemplo
let usuario = 'John';
let edad = 25;
let mensaje = 'Hola';
```

Algunas personas también definen múltiples variables en este estilo multilínea:
```js exemplo 
let usuario = 'John',
  edad = 25,
  mensaje = 'Hola';
```

... O incluso en el estilo "coma primero":

```js exemplo 
let usuario = 'John'
  , edad = 25
  , mensaje = 'Hola';
```

Técnicamente, todas estas variantes hacen lo mismo. Entonces, es una cuestión de gusto personal y estética.


````smart header="`var` instead of `let`"
En scripts anteriores, también puede encontrar otra palabra clave: `var` en vez de `let`:

```js exemplo
*!*var*/!* mensaje = 'Hola';
```

La palabra clave `var` es *casi* igual que `let`. También declara una variable, pero de una manera ligeramente diferente, "vieja escuela".

Hay diferencias sutiles entre `let` y `var`, pero aún no nos importan. Los cubriremos en detalle en el capítulo. <info:var>.
````

##Una analogía de la vida real.

Podemos entender fácilmente el concepto de "variable" si lo imaginamos como una "caja" para datos, con una etiqueta con un nombre único.

Por ejemplo, la variable `mensaje` se puede imaginar como una caja etiquetada como" "mensaje" `con el valor" ¡Hola! "` En ella:

![](variable.svg)

Podemos poner cualquier valor en el cuadro.

También podemos cambiarlo tantas veces como queramos:
```js exemplo
let mensaje;

mensaje = 'Hola!';

mensaje = 'World!'; //valor cambiado

alert(mensaje);
```

Cuando se cambia el valor, los datos antiguos se eliminan de la variable:

![](variable-change.svg)

También podemos declarar dos variables y copiar datos de una a la otra.

```js exemplo
let hola = 'Hola world!';

let mensaje;

*!*
// imita 'Hola world' desde hola hacia mensaje
mensaje = hola;
*/!*

// ahora dos variables contienen los mismos datos
alert(hola); // Hola world!
alert(mensaje); // Hola world!
```

## Nombrando el Variable [#variable-naming]

Hay dos limitaciones en los nombres de variables en JavaScript:

1. El nombre debe contener solo letras, dígitos o los símbolos `$` y `_`.
2. El primer carácter no debe ser un dígito.

Ejemplos de nombres válidos:

```js exemplo
let usuarioName;
let test123;
```

Cuando el nombre contiene varias palabras, [camelCase](https://en.wikipedia.org/wiki/CamelCase) es de uso general Es decir: las palabras van una tras otra, cada palabra comienza con una letra mayúscula:`myVeryLongName`.

Lo que es interesante: el signo de dólar `'$'` y el guión bajo `'_'` también se pueden usar en los nombres. Son símbolos regulares, al igual que las letras, sin ningún significado especial.

Estos nombres son válidos:

```js exemplo untrusted
let $ = 1; // declaró una variable con el nombre "$"
let _ = 2; // y ahora una variable con el nombre "_"

alert($ + _); // 3
```

Ejemplos de nombres de variables incorrectos:

```js exemplo 
let 1a; // no puede comenzar con un dígito

let my-name; // guiones '-' no están permitidos en el nombre
```

```smart header="El Syntax importa"
Las variables llamadas `apple` y` AppLE` son dos variables diferentes.
```

````smart header="Se permiten letras que no están en inglés, pero no se recomiendan."
Es posible utilizar cualquier idioma, incluidas letras cirílicas o incluso jeroglíficos, como este:

```js exemplo
let имя = '...';
let 我 = '...';
```

Técnicamente, no hay ningún error aquí, tales nombres están permitidos, pero existe una tradición internacional de usar el inglés en nombres variables. Incluso si estamos escribiendo un guión pequeño, puede tener una larga vida por delante. Es posible que las personas de otros países necesiten leerlo alguna vez.
````

````warn header="Nombres reservados"
Una lista de nombres reservados (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords), que no se pueden usar como nombres de variables porque son utilizados por la propia languedad.

For example: `let`, `class`, `return`, and `function` are reserved.

The code below gives a syntax error:

```js exemplo 
let let = 5; // can't name a variable "let", error!
let return = 5; // also can't name it "return", error!
```
````

````warn header="Una tarea sin `use strict`"

Normalmente, necesitamos definir una variable antes de usarla. Pero en los viejos tiempos, era técnicamente posible crear una variable mediante una mera asignación del valor sin usar `let`. Esto todavía funciona ahora si no ponemos 'use estricto' en nuestros scripts para mantener la compatibilidad con los scripts antiguos.

```js exemplo no-strict
// nota: no "use strict" en este ejemplo

num = 5; // la variable "num" se crea si no existiera

alert(num); // 5
```

TEsta es una mala práctica y causaría un error en modo estricto:

```js exemplo
"use strict";

*!*
num = 5; // error: num no está definido
*/!*
```
````

## Constantes

Para declarar una variable constante (inmutable), use `const` en lugar de` let`:

```js exemplo
const miCumple = '18.04.1982';
```

Las variables declaradas usando `const` se llaman" constantes ". No pueden ser cambiados. Un intento de hacerlo provocaría un error:

```js exemplo
const miCumple = '18.04.1982';

miCumple = '01.01.2001'; // error, no se puede reasignar la constante!
```

Cuando un programador está seguro de que una variable nunca cambiará, puede declararla con `const` para garantizar y comunicar claramente ese hecho a todos.


###  Constantes con Mayusculas

Existe una práctica generalizada de usar constantes como alias para valores difíciles de recordar que se conocen antes de la ejecución.

Dichas constantes se nombran con letras mayúsculas y guiones bajos.

Me gusta esto:

```js exemplo
const COLOR_ROJO = "#F00";
const COLOR_VERDE = "#0F0";
const COLOR_AZUL = "#00F";
const COLOR_NARANJA = "#FF7F00";

// ... cuando necesitamos elegir un color
let color = COLOR_NARANJA;
alert(color); // #FF7F00
```

Beneficios:

- `COLOR_NARANJA` es mucho más fácil de recordar que`"#FF7F00"`.
- Es mucho más fácil escribir mal `"#FF7F00"` que `COLOR_NARANJA`.
- Al leer el código, `COLOR_NARANJA` s mucho más significativo que `#FF7F00`.

¿Cuándo deberíamos usar mayúsculas para una constante y cuándo deberíamos nombrarla normalmente? Dejémoslo claro.

Ser una "constante" solo significa que el valor de una variable nunca cambia. Pero hay constantes que se conocen antes de la ejecución (como un valor hexadecimal para rojo) y hay constantes que se *calculan* a tiempo, durante la ejecución, pero que no cambian después de su asignación inicial.

Por ejemplo:
```js exemplo
const pedadLoadTime = /* tiempo que tarda un webpedad en cargar */;
```

El valor de `pedadLoadTime` no se conoce antes de la carga de pedad, por lo que se denomina normalmente. Pero sigue siendo una constante porque no cambia después de la asignación.

En otras palabras, las constantes con mayúscula solo se usan como alias para valores "codificados". 

## Nombra todo correctamente

Hablando de variables, hay una cosa más extremadamente importante.

Por favor, nombre sus variables con sensatez. Tómese el tiempo para pensar en esto.

El nombramiento variable es una de las habilidades más importantes y complejas en la programación. Un vistazo rápido a los nombres de variables puede revelar qué código fue escrito por un principiante versus un desarrollador experimentado.

En un proyecto real, la mayor parte del tiempo se dedica a modificar y ampliar una base de código existente en lugar de escribir algo completamente separado desde cero. Cuando volvemos a algún código después de hacer algo más por un tiempo, es mucho más fácil encontrar información que esté bien etiquetada. O, en otras palabras, cuando las variables tienen buenos nombres.

Dedique tiempo a pensar en el nombre correcto para una variable antes de declararla. Hacerlo te recompensará generosamente.

Algunas reglas que se deben seguir son:

- Utilice nombres legibles para humanos como `usuarioName` o` shoppingCart`.
- Manténgase alejado de las abreviaturas o nombres cortos como `a`,` b`, `c`, a menos que realmente sepa lo que está haciendo.
- Hacer nombres máximamente descriptivos y concisos. Ejemplos de malos nombres son `data` y` value`. Tales nombres no dicen nada. Está bien usarlos si el contexto del código hace que sea excepcionalmente obvio a qué datos o valor hace referencia la variable.
- Acuerde los términos dentro de su equipo y en su propia mente. Si un visitante del sitio se llama "usuario", deberíamos nombrar las variables relacionadas `currentusuario` o` newusuario` en lugar de `currentVisitor` o` newManInTown`.

¿Suena simple? De hecho lo es, pero crear nombres de variables descriptivos y concisos en la práctica no lo es. Intentalo.

```smart header="Reusar o crear?"
Y la última nota. Hay algunos programadores perezosos que, en lugar de declarar nuevas variables, tienden a reutilizar las existentes.

Como resultado, sus variables son como cajas en las que las personas arrojan cosas diferentes sin cambiar sus pegatinas. ¿Qué hay dentro de la caja ahora? ¿Quién sabe? Necesitamos acercarnos y verificar.

Tales programadores ahorran un poco en la declaración de variables pero pierden diez veces más en la depuración.

 Una variable extra es buena, no mala.

Los minificadores y navegadores JavaScript modernos optimizan el código lo suficientemente bien, por lo que no creará problemas de rendimiento. El uso de diferentes variables para diferentes valores puede incluso ayudar al motor a optimizar su código.
```

## Resumen

Podemos declarar variables para almacenar datos utilizando las palabras clave `var`,` let` o `const`.

- `let` - es una declaración de variable moderna. El código debe estar en modo estricto para usar `let` en Chrome (V8).
- `var` - es una declaración de variables de la vieja escuela. Normalmente no lo usamos en absoluto, pero cubriremos diferencias sutiles de `let` en el capítulo <info: var>, en caso de que las necesite.
- `const` - es como `let`, pero el valor de la variable no se puede cambiar.

Las variables deben nombrarse de una manera que nos permita comprender fácilmente lo que hay dentro de ellas.
