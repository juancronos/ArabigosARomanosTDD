# TDD Aplicado a Conversor de Numeros Romanos

El objetivo de este código es aprender o practicar el desarrollo guiado por pruebas (TDD) en un problema pequeño: convertir números arabios a [numeros romano](https://es.wikipedia.org/wiki/Numeraci%C3%B3n_romana).


## Números romanos

Los siete símbolos utilizados en los números romanos son:

* `I` = 1
* `V` = 5
* `X` = 10
* `L` = 50
* `C` = 100
* `D` = 500
* `M` = 1000

Los valores numéricos se crean combinando símbolos utilizando los valores más grandes posibles hasta que se alcanza el valor deseado.
Por ejemplo, `VIII` es igual a 8 y` XXXVII` es igual a 37.

Sin embargo, hay algunos casos específicos en los que se utiliza una notación sustractiva:

* `IV` = 4
* `IX` = 9
* `XL` = 40
* `XC` = 90
* `CD` = 400
* `CM` = 900

Entonces, por ejemplo, `XCV` es igual a 95 y` MMXIV` es igual a 2014.

## Test Driven Development

Los conceptos básicos de TDD se pueden resumir describiendo un flujo único conocido como "rojo, verde y refactorizar". Hay 3 pasos:

1. Escribe una prueba que falle (rojo)
2. Hacer que la prueba pase (verde)
3. Refactorizar el código según sea necesario para mantenerlo limpio mientras se pasan las pruebas

Para desarrollar este taller, se repitio estos 3 pasos una y otra vez hasta que se consiguio una solución que funcionaba para todas la pruebas.


## Introducción

Este repositorio está configurado para correr sobre [Node.js] (https://nodejs.org) utilizando el framework de pruebas [mocha] (https://mochajs.org/).

Si no tiene instalado Node.js, primero deberá hacerlo desde [Nodejs.org] (https://nodejs.org). 

Luego, en el directorio raíz de este repositorio, ejecute `npm install` para instalar mocha.

Luego ejecute `npm test` para iniciar el marco de prueba.

Ahora puede comenzar a escribir su primera prueba en la carpeta `test / roman-tests.js`. Por ejemplo, puede comenzar agregando esta prueba dentro del bloque `describe`:

```
it('should convert 1 to I', function () {
  var result = roman.toRoman(1);
  assert.equal(result, 'I');
});
```

Luego se modifico el metodo `toRoman` dentro `roman.js` para que devuelva` 'I'`

Se debe repetir con cada prueba para finalmente refactorizar el codigo, estos son los pasos de rojo, verde y refactorizar.

## Conclusión

Al realizar varias veces el metodo rojo, verde y refactorizar se evidencia ciero patrón que nos permite resolver el problema de forma más general y no solo para números especificos. Por lo que se llega la solucion general de organizar en un hashmap los posibles numeros romanos y su valores e ir restando del número que queremos convertir cada numero solo si es mayoy o igual, e ir colocando la letra romana a la derecha.
