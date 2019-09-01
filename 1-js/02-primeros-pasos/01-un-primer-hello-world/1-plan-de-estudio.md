# Hello, world!

¡Hola Mundo!
El tutorial que está leyendo trata sobre el núcleo de JavaScript, que es independiente de la plataforma. Más adelante, aprenderá sobre Node.JS y otras plataformas que lo usan.

Pero necesitamos un entorno de trabajo para ejecutar nuestros scripts y, dado que este libro está en línea, el navegador es una buena opción. Mantendremos la cantidad de comandos específicos del navegador (como alerta) al mínimo para que no pase tiempo en ellos si planea concentrarse en otro entorno (como Node.JS). Nos centraremos en JavaScript en el navegador en la siguiente parte del tutorial.

## The "script" tag

Los programas de JavaScript se pueden insertar en cualquier parte de un documento HTML con la ayuda de la etiqueta `<script>`.

Por ejemplo:

```html run height=100
<!DOCTYPE HTML>
<html>

<body>

  <p>Before the script...</p>

*!*
  <script>
    alert( 'Hello, world!' );
  </script>
*/!*

  <p>...After the script.</p>

</body>

</html>
```

```online
You can run the example by clicking the "Play" button in the right-top corner of the box above.
```

La etiqueta `<script>` contiene código JavaScript que se ejecuta automáticamente cuando el navegador procesa la etiqueta.

## Modern markup

La etiqueta `<script>` tiene algunos atributos que rara vez se usan hoy en día, pero todavía se pueden encontrar en el código antiguo:

El atributo `type`  <code>&lt;script <u>type</u>=...&gt;</code>
: El antiguo estándar HTML, HTML4, requería un script para tener un "tipo". Por lo general, era `type ="text/javascript"`. Ya no se requiere. Además, el estándar HTML moderno, HTML5, cambió totalmente el significado de este atributo. Ahora, se puede usar para módulos JavaScript. Pero ese es un tema avanzado; Hablaremos de módulos en otra parte del tutorial.

El atributo `language` <code>&lt;script <u>language</u>=...&gt;</code>
: Este atributo estaba destinado a mostrar el idioma del guión. Este atributo ya no tiene sentido porque JavaScript es el idioma predeterminado. No hay necesidad de usarlo.

Comentarios antes y después de los guiones.
: En libros y guías muy antiguos, puede encontrar comentarios dentro de las etiquetas `<script>`, como esta:
    ```
    
    <!-- Hola soy un comentario usado para documentar mi codigo -->
    
    ```


## External scripts

Si tenemos mucho código JavaScript, podemos ponerlo en un archivo separado.

Los archivos de script se adjuntan a HTML con el atributo `src`:

```html
<script src="/path/to/script.js"></script>
```


Aquí, `/ejemplo/de/guia/script.js` es una ruta absoluta al archivo de script (desde la raíz del sitio).

También puede proporcionar una ruta relativa desde la página actual. Por ejemplo, `src="script.js"` significaría un archivo `"script.js"` en la carpeta actual.

También podemos dar una URL completa. Por ejemplo:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js"></script>
```

Para adjuntar varios scripts, use varias etiquetas:

```html
<script src="/js/script1.js"></script>
<script src="/js/script2.js"></script>
…
```

## Summary

- Podemos usar una etiqueta `<script>` para agregar código JavaScript a una página.
- Los atributos `type` e` language` no son obligatorios.
- Se puede insertar un script en un archivo externo con `<script src="path/to/script.js"> </script>`.


Hay mucho más que aprender sobre los scripts del navegador y su interacción con la página web. Pero tengamos en cuenta que esta parte del tutorial está dedicada al lenguaje JavaScript, por lo que no debemos distraernos con implementaciones específicas del navegador. Usaremos el navegador como una forma de ejecutar JavaScript, lo cual es muy conveniente para la lectura en línea, pero solo uno de muchos.