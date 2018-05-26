# Ejercicio 2

1. Dar una definición de tipo de dato.
2. ¿Qué es un tipo predefinido elemental? Dar ejemplos.
3. ¿Qué es un tipo definido por el usuario? Dar ejemplos.

#

1. Un tipo de dato puede ser concebido de tres formas diferentes que se complementan entre si:
+ Desde el punto de vista **denotacional**, es un conjunto de valores sobre un dominio.
+ Desde el punto de vista **constructivo**, puede ser:
* *Primitivo* (built-in o predefinido): provisto por el lenguaje.
* *Compuesto* (composite o derivado): empleando constructores de tipos.
+ Desde el punto de vista de la **abstracción**, puede ser:
* Una interfaz a una representación.
* Conjunto de operaciones con semántica bien definida y consistente.
2. Un tipo predefinido elemental es aquel que ya viene definido con el lenguaje y que no esta compuesto de otros tipos. Ejemplo: Los char e integer son predefindos(vienen ya por defecto en el lenguaje) de tipo elemental dado que no se puede dividirlos en otros tipos. Un string podria ser predefinido(depende el lenguaje), pero no es elemental ya que un string es un conjunto de char.
3. Un tipo definido por el usuario es un tipo que se define por el tipo predefinido que el usuario elije. Algunso ejemplos son los arreglos o las listas. Una lista por si sola no es nada, no tiene sentido; no asi una lista de enteros o una lista de strings en la cual su tipo ya ha sido definido por el usuario.
