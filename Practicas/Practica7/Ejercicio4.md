# Ejercicio 4

1. Definir mutabilidad e inmutabilidad respecto a un dato. Dar ejemplos en al menos 2 lenguajes. ​ TIP: indagar sobre los tipos de datos que ofrece Python y sobre la operación #freeze en los objetos de Ruby.
2. Dado el siguiente código:

```
a ​=​ Dato.new(1)
a ​=​ Dato.new(2)
```

¿Se puede afirmar entonces que el objeto “Dato.new(1)” es mutable? Justificar la respuesta sea por afirmativa o por la negativa.

1. La mutabilidad de un dato es una propiedad que establece que un objeto puede ser cambiado durante su ejecucion; por su parte, la inmutabilidad es todo lo contrario: establece que el estado de un objeto no puede ser modificado una vez creado.  
En ruby, este concepto es tan literal en el sentido de que permite crear constantes y mediante el metodo freeze hacer que su valor no cambie.  
En python, ocurre algo diferente. Los números, los strings y las tuplas son inmutables. Por el contrario, las listas son mutables.  
Esto no quiere decir que, estrictamente, un numero o un string no puedan cambiar de valor. El concepto de inmutabilidad, en este caso, se aplica a que si yo tuviera dos variables, por ejemplo, "x" e "y" y quisiera asignarle el valor de "x" a "y" y luego cambiara "x", el valor que yo estableci en "y" sigue siendo el que yo antes habia definido. El asunto es que si el objeto fuera mutable y yo hiciera lo anterior, "x" e "y" tendrian en todo momento el mismo valor("y" seria un alias de "x").

2. Si el codigo fuera python, el dato no seria mutable ya que es un numero y los numeros no mutan.
