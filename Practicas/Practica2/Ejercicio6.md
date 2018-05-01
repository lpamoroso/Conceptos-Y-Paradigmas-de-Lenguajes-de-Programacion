Ejercicio 6
======
Defina en BNF(Gramática de contexto libre desarrollada por Backus-Naur) la gramática para la definición de una palabra cualquiera.

Solución
------
G = (N, T, S, P)  
N = {< palabra > < letra_mayus > < letra_minus >}  
T = {a..z, A..Z}  
S = {< palabra >}  
P = {  
&nbsp;&nbsp;< palabra > ::= < letra_mayus >< palabra > | < letra_minus >< palabra > | < letra_minus >  
&nbsp;&nbsp;< letra_mayus > ::= A|B|C|...|X|Y|Z  
&nbsp;&nbsp;< letra_minus > ::= a|b|c|...|x|y|z   
}  
