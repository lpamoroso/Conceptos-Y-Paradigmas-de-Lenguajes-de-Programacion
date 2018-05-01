Ejercicio 7
======
Defina, en EBNF, la gramática para la definición de números reales. Inténtelo desarrollar para BNF y explique las diferencias con la utilización de la gramática EBNF.

Solución
------
BNF:  
G = (N, T, S, P)    
N = { < numero_real >, < digito >, < coma >, < menos > }  
T = { 0..9, '-', ',' }  
S = { < numero_real > }  
P =  
{  
&nbsp;&nbsp;< numero_real > ::= < digito >< numero_real > | < menos >< digito >< numero_real > | < digito >< coma >< numero_real > |  < digito >  
&nbsp;&nbsp;< digito > ::= 0|1|2|...|7|8|9  
&nbsp;&nbsp;< coma > ::= ','  
&nbsp;&nbsp;< menos > ::= '-'  
}  

EBNF:  
G = (N, T, S, P)    
N = { < numero_real >, < digito >, < coma >, < menos > }  
T = { 0..9, '-', ',' }  
S = { < numero_real > }  
P =  
{  
&nbsp;&nbsp;< numero_real > ::= [< menos >]{< digito >}+[< coma >{< digito >}+]  
&nbsp;&nbsp;< digito > ::= 0|1|2|...|7|8|9  
&nbsp;&nbsp;< coma > ::= ','  
&nbsp;&nbsp;< menos > ::= '-'  
}  

Claramente se puede observar la diferencia entre BNF y EBNF: mientras que EBNF es sumamente expresivo, BNF no lo es tanto; además BNF no es tan simple de leer como EBNF.  
Otra utilidad de EBNF está en el caso de las repeticiones: mientras que en BNF el unico recurso disponible es el de la recursión(un recurso complejo para implementar y algo engorroso por los múltiples caminos que puede tomar la recursión). EBNF resuelve el problema con metasímbolos para indicar la repetición, definiendo uno específicamente para la repetición 0..* y otro para la 1..*, lo cual resuelve todos los problemas derivados de la recursión.
