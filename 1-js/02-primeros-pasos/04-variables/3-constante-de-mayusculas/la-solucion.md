importance: 4

---

Generalmente usamos mayúsculas para constantes que están "codificadas". O, en otras palabras, cuando el valor se conoce antes de la ejecución y se escribe directamente en el código.

En este código, `cumpleaños` es exactamente así. Entonces podríamos usar mayúsculas para ello.

En contraste, 'edad' se evalúa en tiempo de ejecución. Hoy tenemos una edad, un año después tendremos otra. Es constante en un sentido que no cambia a través de la ejecución del código. Pero es un poco "menos constante" que `cumpleaños`, se calcula, por lo que debemos mantener en minúscula.\


```js
const CUMPLEANOS = '18.04.1982'; 

const EDAD = someCode(CUMPLEANOS); 
```