# 📦 Nuevas variables - Creación, Actualización y Ambitos

_Todos los scripts pueden ser usados directamente en la consola de tu navegador_

## Refrescamiento... Ámbito de variables

En javascript tenemos 3 maneras de declarar variables, 
`var` que es la manera que solemos utilizar, y ahora en la nueva versión ES6 `let` y `const`, de las que estaremos comentando un poco más adelante.

```js
var width = 100; 
let height = 200;
const key = 'abc123'

```

Una de las utilidades de las  variables `var` es que se pueden reasignar y por ende actualizar su valor: 

```js 
var width = 100; 
console.log(width); // 100
width = 200; 
console.log(width); // 200
```

En el ejemplo anterior, lo que hacemos básicamente es volver a declarar `width` pero en esta oportundidad con un nuevo valor `200`. Si ejecutamos el código anterior la salida será exactamente la misma. Una cosa que vale la pena acotar es que, al momento de reasignar el valor a una variable, no es necesario volver a declararla con la palabra reservada `var`, ya que estaríamos creando la misma variable 2 veces en el mismo ámbito.

Cuándo hablamos del  ***ámbito*** de una variable, hacemos referencia básicamente:
> al momento en que ésta se encuentra disponible para utilizar.

Todas las variables declaradas en el siguiente fragmento de código son globales, _con esto indicamos que están disponibles desde cualquier parte en las que se le invoque_. 

Las variables `var` son conocidas por tener un ámbito de función, lo que quiere decir que estarán disponibles solo en el contexto donde se les declare. ¿Qué pasaría si declaro una función: 

```js 

function setWidth () {
  var width = 100;
  console.log(width);
}

setWidth() // 100
```

Debido a que `width` está siendo declarada dentro de la función `setWidth()` el resultado retornado es exactamente el esperamos 100. Pero, ¿que pasara si queremos conocer el valor de `width` fuera de contexto donde fué declarada?

```js 

function setWidth () {
  var width = 100;
  console.log(width);
}

setWidth() // 100
console.log(width); // Uncaught ReferenceError: width is not defined
```
¡Error! la variable `width` solo se encuentra disponible dentro del ámbito de la función `setWidth`, y por ello no podemos acceder cuando intentamos consultarle desde fuera. Para que este caso sea factible, debemos hacer un pequeño refactor a nuestro código: 


```js 
var width; 
function setWidth () {
  width = 100;
  console.log(width);
}

setWidth() // 100
console.log(width) // 100; 

```

Pero recuerda que siempre es mejor tener nuestras variables declaradas solo justo donde la utilizaremos. 

```js

var age = 100; 
if (age > 12) {
  var dogYears = age * 7; 
  console.log(`You're ${dogYears} dog years old`); //
}

var width = 100; 
let height = 200;
const key = 'abc123'

```


## let vs const

## let y const en el mundo real 

## zona muerta temporal

## ¿var está muerta? ¿Qué debería utilizar?
