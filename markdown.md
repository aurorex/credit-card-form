# FUNCTION-SCOPE-JS

###  El proceso de Contexto de Ejecución se dan dos fases: la fase de **Creación** y la fase de **Ejecución**.

## Creación:

- Se crea el objeto Window y la variable This por default

- se crean objetos globales:
  la función $(document).ready 

- se crean objetos locales : 

  . 6 variables($inputCard,$inputMonth,$inputYear,$buttonNext,regexOnlyNumbers,labelErrorOrSuccessMessages) que tienen un valor(elementos del dom y  expresiones regulares) asignado.En el scope de la función $(document).ready se consideran globales.
  . 5 funciones de tipo **statement**(en el scope de la función $(document).ready se consideran globales).
  . evento **input**(en el scope de la función $(document).ready se considera global).
  . las variables regex,creditCardNumber,arr,sumaTotal y arr[index].

## Proceso de ejecucuión:

- se ejecuta la función $(document).ready

- se ejecuta la función console.log-->linea 3

- se declaran 6 variables-->linea 6-11 

- el evento input se coloca en la pila de ejecución,siempre y cuando ésta este vacía,al ejecutarse el evento se llama a la función isValidCreditCard-->linea 15

- se ejcuta la función isValidCreditCard y dentro de ella se declara en la  variable creditCardNumber una función soloNumeros(), que se ejecuta en la línea 36, que a su vez llama a la función longitud(numberCard) que se ejecuta en la linea 29

- si se cumple la 1ra condición if(creditCardNumber !== undefined) que tiene la 2da condición if (sumaTotal % 10 === 0), dentro de esta condición interna de la primera se ejecutará un console.log('Es una tarjeta valida')-->linea 64, y se llamará a la función activeButton()-->65 que se ejecutará en la línea 19.

- si no se cumple la segunda condición ejecuta console.log('No es un numero valido')-->67 y llama a la función desactiveButton()-->68 que se ejecutará en la linea 24.

- si no se cumple la primera condición, se ejcutará console.log('Verifique el numero de su tarjeta')-->71 y se llamará a la función desactiveButton()-->72 que se ejecutará en la linea 24.
