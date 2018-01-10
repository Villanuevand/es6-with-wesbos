# 📦 Mejoras en Funciones - Flechas (a.k.a: arrows) y Argumentos por Defecto

_Todos los scripts pueden ser usados directamente en la consola de tu navegador_

Una de las cosas que más me costó sobre este módulo fue el hecho de escribir, ***Funciones Flecha*** en vez de ***Arrow Functions***, pero es la traducción correcta, y aunque suene raro, ese es el término que usaremos. 🙂

### Contenido

- [Introducción a funciones flecha](#introducci%C3%B3n-a-funciones-flecha)
- [Más ejemplos de funciones flechas](#m%C3%A1s-ejemplos-de-funciones-flechas)
- [Funciones flecha y el `this`](#funciones-flecha-y-el-this)
- [Argumentos por defecto](#argumentos-por-defectos)
- [Cuando NO usar una función flecha](#cuando-no-usar-una-funci%C3%B3n-flecha)
- [Ejercicios](#ejercicios)

## Introducción a funciones flecha

`ES6` ha introducido las _funciones flechas_, o _arrow functions_ por su nombre en ingles, que en mi opinion tiene 3 grandes beneficios: 

- Son más concisas que las funciones regulares.
- Tiene `return` implicito, lo que nos permite escribir funciones más ingeniosas en una sola línea.
- No hace `rebind` de los valores cuando se usan dentro de una función común. Lo que es realmente útil cuando haces cosas como, manejadores de click.

Vamos a mirar muchos ejemplos y estaremos usando muchas _funciones flechas_ en todos lados a lo largo de este curso.

Ahora...Tenemos este arreglo llamado `names` y quiero agregarle `bos` al final de cada uno de ellos. Normalmente usaría algo así: 

```js
const names = ['wes', 'kait', 'lux'];
const fullNames = names.map(function (name) {
  return `${name} bos`;
});
```

Creamos una variables `fullNames` donde serán guardados los datos, que  con la ayuda del método `map()`, iteraremos el arreglo de nombres `names`. A `map()` le pasamos una función anónima regular, donde como parámetro de esa función está `name`, que contendré el valor de cada item, resultante de la iteración. Retornaremos un `string template`, _si no entiendes que es esto, ¡tranquilo! hablaremos en el próximo módulo sobre eso_, con el valor del item en el momento de la iteración `return ${name}`.

```js
const names = ['wes', 'kait', 'lux'];
const fullNames = names.map(function (name) {
  return `${name} bos`;
});

console.log(fullNames); // ['wes bos', 'kait bos','lux bos'];
```

¡Funciona perfecto!, pero esto no es una _función flecha_, vamos a buscar la manera de refactorizar esto: 


```js
const names = ['wes', 'kait', 'lux'];
const fullNames = names.map(function (name) {
  return `${name} bos`;
});

console.log(fullNames); // ['wes bos', 'kait bos','lux bos'];

// Refactor 
const fullNames2 = names.map((name) => {
  return `${name} bos`;
});

console.log(fullNames2); // ['wes bos', 'kait bos','lux bos'];
```

En `fullNames2` lo que hicimos fué, remover la palabra reserva `function`, conservamos el parametro `name` y agregamos la llamada ***fat arrow*** o ***flecha gruesa / gorda*** que no es más que el símbolo `igual =` y `mayor que >` ,si vienes de otros lenguajes quizas te sea familiar, pero en javascript es la primera vez que aparece. 

La salida de `fullNames2` es exactamente la misma que `fullNames`, a diferencia que en la segunda estamos usando una _función flecha_. 

Esto se puede seguir refactorizando: 

```js
const names = ['wes', 'kait', 'lux'];
const fullNames = names.map(function (name) {
  return `${name} bos`;
});

console.log(fullNames); // ['wes bos', 'kait bos','lux bos'];

// Refactor 
const fullNames2 = names.map((name) => {
  return `${name} bos`;
});

console.log(fullNames2); // ['wes bos', 'kait bos','lux bos'];

// Otro Refactor...
const fullNames3 = names.map(name => {
  return `${name} bos`;
});

console.log(fullNames3); // ['wes bos', 'kait bos','lux bos'];
```

Si la cantidad de parámetros que recibe una _función flecha_ es solamente 1 puedes remover los paréntesis `( )` y esta seguirá funcionando sin ningún problema, cuando posees más de 1 parámetro es obligatorio que vuelvas a usar los paréntesis para definir los parámetros. 

Si quieres usar o no los paréntesis cuando la función posee 1 solo parámetro quedará a tu elección, en mí caso no los uso.

El ejemplo anterior, se puede seguir refactorizando, ¿QUE?, si como lo lees, podemos usar una de las características principales de las _funciones flechas_, el `return` implicito.

> #### ¿Qué es un `return` explicito?  
> Es cúando escribes explicitamente la palabra `return` para retornar algo en una función.

Muchos `callbacks` que escribimos en javascript poseen solo 1 línea un `return` explicito, pero ya eso no será necesario.

> #### ¿Qué debo hacer con el `return`?


```js
const names = ['wes', 'kait', 'lux'];
const fullNames = names.map(function (name) {
  return `${name} bos`;
});

console.log(fullNames); // ['wes bos', 'kait bos','lux bos'];

// Refactor 
const fullNames2 = names.map((name) => {
  return `${name} bos`;
});

console.log(fullNames2); // ['wes bos', 'kait bos','lux bos'];

// Otro Refactor...
const fullNames3 = names.map(name => {
  return `${name} bos`;
});

console.log(fullNames3); // ['wes bos', 'kait bos','lux bos'];

// Un nuevo refactor...
const fullNames4 = names.map(name =>  `${name} bos`);

console.log(fullNames4); // ['wes bos', 'kait bos','lux bos'];

```

En `fullNames4` estamos viendo una _función flecha_ con `return` implicito, y lo que hicimos fué colocarlo todo en una sola línea, eliminar la  palabra `return` y las _llaves_ `{ }`. Al eliminar las llaves, `{ }` se transformará en un retorno implícito, con lo que no necesitares especificar que retornaremos la variable `name`, sino que se asume que haremos esto.


En caso de que no necesites retornar ningún parámetro en tu _función flecha_ puedes usar paréntesis vacíos sin problema.

```js
const names = ['wes', 'kait', 'lux'];

const fullNames5 = names.map(() =>  `cool bos`);

console.log(fullNames5); // ['cool bos', 'coll bos','coll bos'];
```

Otra de las cosas que quízas deberías saber de las _funciones flecha_ almenos en este momento, no sabemos si en futuras versiones se mantenga, es que las _funciones flecha_ son funciones anónimas. 

> #### ¿Qué es una función anónima?

¡No!, mejor ...

> #### ¿Qué es una función nombrada?
> Son aquellas funciones que tienen definido un nombre... ¡Qué genio!
```js
function sayMyName () {
    alert(`Hello ${name}`);
}
```

¡Eso es una función nombrada, y uno de sus principales beneficios es que si tienes un error, y estas inspeccionando tu aplicación por algún error, este puede aparecer con el nombre y la línea donde ocurre la falla, mientras que con las _funciones flecha_ esto no será así. 

Todas las _funciones flecha_ qué hemos realizado nínguna tienen nombre, pero puedes nombrarlas usando una variable.

```js
const sayMyName = (name) => { `Hello ${name}`};
sayMyName('Wes');
```

Esto es lo que se conoce como una _función declarada_ o _function declaration_ en ingles.


[Ir arriba 👆](#contenido)

## Más ejemplos de funciones flechas

[Ir arriba 👆](#contenido)

## Funciones flecha y el `this`

[Ir arriba 👆](#contenido)

## Argumentos por defecto

[Ir arriba 👆](#contenido)

## Cuando NO usar una función flecha

[Ir arriba 👆](#contenido)

## Ejercicios 

[Ir arriba 👆](#contenido) o  [Próximo módulo 🚀](/modulos/modulo-03.md)
