## En el siguiente trabajo identificaremos lo siguiente:
 - Funciones globales: son las funciones que no se encuentran dentro de otra función.

 - Funciones locales: son las funciones que se encuentran dentro de otra función.

 - Funciones de callback: son funciones que pasan como parámetros a otra función.
 
 - Function expression: se crea una función anónima asociada a una variable.
 
 - Funciones statement: son funciones declaradas, requieren que se les especifique el nombre de la misma y se ejecutarán cuando sean llamadas.
 
 - Clousure: es la capacidad de las variables de recordar su entorno.
 
 - Scope: es el alcance que tiene una variable dentro de una función el cual determina la accesibilidad de las mismas.
 
 - Contextos de ejecución: el contexto de ejecución se crea por cada función declarada que se encuentre.
 
 - Funciones que forman parte de la pila de ejecución (stack execution): son funciones que son posicionadas(apiladas) a medida de la llamada de las mismas.
 
 - Funciones que forman parte de la cola de eventos (event queue)

****
1. Funciones globales: 

  - Tenemos una función global respecto al contexto de ejecución document y con respecto al contexto global de ejecución window esta es una función local.
  * funcion anónima:
  $(document).ready(function() {};

  - Variables globales: con respecto al contexto de ejecución document tenemos 6 variables, y si nos referimos al contexto global de ejecución window estas mismas son locales.
  * $inputCard
  * $inputMonth
  * $inputYear
  * $buttonNext
  * regexOnlyNumbers
  * labelErrorOrSuccessMessages

2. Funciones locales: tenemos 6 funciones locales respecto al contexto de ejecución document, siendo una de ellas función anónima.
* función anónima: $inputCard.on('input', function() {}
* function activeButton() {}
* function desactiveButton() {}
* function longitud(input) {}
* function soloNumeros(input) {}
* function isValidCreditCar(numberCard){}

3. Funciones callback: encontramos 1 función callback.
* var creditCardNumber = soloNumeros(longitud(numberCard));

4. Function expression: en este caso no encontramos function expression ya que no tienen la siguiente estructura:
* ejemplo: var ejemplo = function(part) {}

5. Function statement: encontramos 5, son las siguientes:
* function activeButton() {}
* function desactiveButton() {}
* function longitud(input) {}
* function soloNumeros(input) {}
* function isValidCreditCard(numberCard) {}

6. Clousure: es una función que recuerda sus variables externas y puede acceder a ellas.

7. Scope: pueden ser local scope y global scope, encontramos 3: 
  - global scope: con respecto al contexto de ejeción document tenemos  los siguientes scope:
 
  * $(document).ready(function() {   
    var $inputCard = $('#card-number');
    var $inputMonth = $('.input-month');
    var $inputYear = $('.input-year');
    var $buttonNext = $('#next');
    var regexOnlyNumbers = /^[0-9]+$/;
    var labelErrorOrSuccessMessages = $('label[for="card-number"]');
  };

  - Scope local: las variables en el scope local solo se les puede acceder estando dentro de dicha función:

  * function soloNumeros(input) {
    var regex = /^[0-9]+$/;
    if (regex.test(input)) {
      return input;
    }
  }

* function isValidCreditCard(numberCard) {
    var creditCardNumber = soloNumeros(longitud(numberCard));
  }

8. Contextos de ejecución:
  * Contexto de ejecución de document.
  * Contexto global de ejecución.
  * Contexto de ejecución de la function activeButton() {}
  * Contexto de ejecución de la function desactiveButton() {}
  * function longitud() {}
  * Contexto de ejecución de la function soloNumeros(input) {}
  * Contexto de ejecución de la function isValidCreditCard(numberCard) {}

9. Funciones que forman parte de la pila de ejecución: encontramos 7
* Contexto de ejecución de function desactiveButton() {}
* Contexto de ejecución de function activeButton() {}
* Contexto de ejecución de function longitud() {}
* Contexto de ejecución de function soloNumeros() {}
* Contexto de ejecución de function isValidCreditCard(numberCard) {}
* Contexto de ejecución de document() {}
* Contexto global de ejecución

10. Funciones que forman parte de la cola de eventos: encontramos 1

* $inputCard.on('input', function() {}