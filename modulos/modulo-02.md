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
- Tiene `return` implicito, lo que nos permite escribir funciones ms ingeniosas en una sola línea.
- No hace `rebind` de los valores cuando se usan dentroi de una función común. Lo que es realmente útil cuando haces cosas como, manejadores de click.

Vamos a mirar muchos ejemplos y estaremos usando muchas _funciones flechas_ en todos lados a lo largo de este curso.

Ahora...Tenemos este arreglo llamado `names` y quiero agregarle `bos` al final de cada uno de ellos. Normalmente usaría algo así: 

```js
const names = ['wes', 'kait', 'lux'];
const fullNames = names.map(function (name) {
  return `${name} bos`;
});
```

Creamos una variables `fullNames` donde serán guardados los datos, que  con la ayuda del método `map()`, iteraremos el arreglo de nombres `names`. A `map()` le pasamos una función anónima regular, donde se le pasa como parámetro `name`, que contendré el valor de cada item, resultante de la iteración. Retornaremos un `string template`, si no entiendes que es esto, ¡tranquilo! hablaremos en el próximo módulo sobre eso, con el valor del item en el momento de la iteración `return ${name}`.

```js
const names = ['wes', 'kait', 'lux'];
const fullNames = names.map(function (name) {
  return `${name} bos`;
});

console.log(fullNames); // ['wes bos', 'kait bos','lux bos'];
```

¡Funciona perfecto!, pero esto no es una _función flecha_


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
