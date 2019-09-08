# La estructura de nuestro Codigo

Lo primero que estudiaremos son los bloques de construcción de código.

## Declaraciones

Las declaraciones son construcciones de sintaxis y comandos que realizan acciones.

Ya hemos visto una declaración, `alert('Hello, world!')`, que muestra el mensaje "Hello, world!".

Podemos tener tantas declaraciones en nuestro código como queramos. Las declaraciones se pueden separar con un punto y coma.

Por ejemplo, aquí dividimos "Hello World" en dos alertas:

```js ejemplo
alert('Hello'); alert('World');
```

Por lo general, las declaraciones se escriben en líneas separadas para que el código sea más legible:

```js ejemplo
alert('Hello');
alert('World');
```

## punto y coma = `;`

Se puede omitir un punto y coma en la mayoría de los casos cuando existe un salto de línea.

Esto también funcionaría:

```js ejemplo
alert('Hello')
alert('World')
```

Aquí, JavaScript interpreta el salto de línea como un punto y coma "implícito". Esto se denomina [inserción automática de punto y coma] (https://tc39.github.io/ecma262/#sec-automatic-semicolon-insertion).

## En la mayoría de los casos, una nueva línea implica un punto y coma. ¡Pero "en la mayoría de los casos" no significa "siempre"!

Hay casos en que una nueva línea no significa un punto y coma. Por ejemplo:

```js ejemplo
alert(3 +
1
+ 2);
```

El código genera `6` porque JavaScript no inserta punto y coma aquí. Es intuitivamente obvio que si la línea termina con un signo más `"+"`, entonces es una "expresión incompleta", por lo que no es necesario el punto y coma. Y en este caso eso funciona según lo previsto.

## Pero hay situaciones en las que JavaScript "no puede" asumir un punto y coma donde realmente se necesita ##

Los errores que ocurren en tales casos son bastante difíciles de encontrar y corregir.

````smart header="An example of an error"
Si tiene curiosidad por ver un ejemplo concreto de tal error, consulte este código:

```js ejemplo
[1, 2].forEach(alert)
```

No es necesario pensar aún en el significado de los corchetes `[]` y `forEach`. Los estudiaremos más tarde. Por ahora, solo recuerde el resultado del código: muestra `1` y luego `2`.

Ahora, agreguemos una 'alerta' antes del código y * no * terminemos con un punto y coma:

```js ejemplo
alert("There will be an error")

[1, 2].forEach(alert)
```

Ahora, si ejecutamos el código, solo se muestra la primera `alerta` y luego tenemos un error!

Pero todo vuelve a estar bien si agregamos un punto y coma después de `alert`:
```js ejemplo
alert("All fine now");

[1, 2].forEach(alert)  
```

Ahora tenemos el mensaje "Todo bien ahora" seguido de `1` y` 2`.

El error en la variante sin punto y coma ocurre porque JavaScript no asume un punto y coma antes de los corchetes `[...]`.

Entonces, debido a que el punto y coma no se inserta automáticamente, el código en el primer ejemplo se trata como una sola declaración. Así es como el motor lo ve:

```js ejemplo
alert("There will be an error")[1, 2].forEach(alert)
```

Pero deberían ser dos declaraciones separadas, no una. Tal fusión en este caso es simplemente incorrecta, de ahí el error. Esto puede suceder en otras situaciones.
````

Recomendamos poner punto y coma entre las declaraciones, incluso si están separadas por líneas nuevas. Esta regla es ampliamente adoptada por la comunidad. Observemos una vez más: * es posible * omitir los punto y coma la mayor parte del tiempo. Pero es más seguro, especialmente para un principiante, usarlos.

## Commentarios

A medida que pasa el tiempo, los programas se vuelven cada vez más complejos. Se hace necesario agregar * comentarios * que describan lo que hace el código y por qué.

Los comentarios se pueden poner en cualquier lugar de un script. No afectan su ejecución porque el motor simplemente los ignora.

**Los comentarios de una línea comienzan con dos caracteres de barra diagonal `//`.**

El resto de la línea es un comentario. Puede ocupar una línea completa propia o seguir una declaración.

Como aquí:
```js ejemplo
// Este comentario ocupa una línea propia
alert('Hello');

alert('World'); // Este comentario sigue la declaración
```

**Los comentarios multilínea comienzan con una barra diagonal y un asterisco <code>/&#42;</code> y termina con un asterisco y una barra diagonal <code>&#42;/</code>.**

Como aquí:

```js ejemplo
/* Un ejemplo con dos mensajes.
Este es un comentario multilínea.
*/
alert('Hello');
alert('World');
```

El contenido de los comentarios se ignora, así que si ponemos código dentro <code>/&#42; ... &#42;/</code>, No se ejecutará.

A veces puede ser útil deshabilitar temporalmente una parte del código:

```js ejemplo
/* Comentando el código
alert('Hello');
*/
alert('World');
```

```Usa accesos rapidos del teclado
En la mayoría de los editores, se puede comentar una línea de código presionando el `key:Ctrl+/` tecla de acceso rápido para un comentario de una sola línea y algo así como `key:Ctrl+Shift+/` -- para comentarios multilínea (seleccione un fragmento de código y presione la tecla de acceso rápido). Para Mac, intente `key:Cmd` en vez de `key:Ctrl`.
```

````¡Los comentarios anidados no son compatibles!
Puede que no haya `/*...*/` dentro de otro `/*...*/`.

Tal código morirá con un error:

```js ejemplo
/*
  /* commentario invalido !! */
*/
alert( 'World' );
```
````


Por favor, no dude en comentar su código.

Los comentarios aumentan la huella general del código, pero eso no es un problema en absoluto. Hay muchas herramientas que minimizan el código antes de publicar en un servidor de producción. Quitan los comentarios, por lo que no aparecen en los scripts de trabajo. Por lo tanto, los comentarios no tienen ningún efecto negativo en la producción.

Más adelante en el tutorial habrá un capítulo <info:code-quality> que también explica cómo escribir mejores comentarios.
