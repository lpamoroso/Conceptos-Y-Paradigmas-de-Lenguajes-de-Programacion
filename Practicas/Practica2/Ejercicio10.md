Ejercicio 10
======
1. Defina con EBNF la gramática para una expresión numérica, dónde intervienen variables y números. Considerar los operadores +, -, * y / sin orden de prioridad. No considerar el uso de paréntesis.
2. A la gramática definida en el ejercicio anterior agregarle prioridad de operadores.

Solución
------
1.
```
1. G = (N, T, S, P)  
N = { < sentencia >, < digito >, < entero >, < operacion > }  
T = { 0..9, '+', '-', '*', '/' }  
S = { < sentencia > }  
P =  
{  
  < sentencia > ::= [< variable > | < entero >]{< operador >[< variable > | < entero >]}*
  < variable > ::= {[< letra_mayus > | < letra_minus >]}+
  < entero > ::= {< digito >}+  
  < digito > ::= 0|1|2|3|...|7|8|9  
  < operacion > ::= +|-|*|/
  < letra_minus > ::= a..z  
  < letra_mayus > ::= A..Z  
}  
```
2.
```
1. G = (N, T, S, P)
N = { < sentencia >, < digito >, < entero >, < operacion > }
T = { 0..9, '+', '-', '*', '/' }
S = { < sentencia > }
P =
{
  < sentencia > ::= < expresion >{< operacion_con_prioridad >< expresion >}*
  < expresion > ::= [< variable > | < entero >]{< operacion_sin_prioridad >[< variable > | < entero >]}*
  < variable > ::= {[< letra_mayus > | < letra_minus >]}+
  < entero > ::= {< digito >}+
  < digito > ::= 0|1|2|3|...|7|8|9
  < operacion_con_prioridad > ::= *|/
  < operacion_sin_prioridad > ::= +|-
  < letra_minus > ::= a..z
  < letra_mayus > ::= A..Z
}
```
