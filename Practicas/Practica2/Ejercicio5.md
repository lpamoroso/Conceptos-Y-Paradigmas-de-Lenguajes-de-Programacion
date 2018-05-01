Ejercicio 5
======
Dada la siguiente gramática escrita en BNF:  
G = ( N, T, S, P)  
N = {<número_entero>, <dígito> }  
T = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}  
S = <número_entero>  
P = {  
&nbsp;&nbsp;<número_entero>::=<dígito><numero_entero> | <numero_entero><dígito> | <dígito>  
&nbsp;&nbsp;<dígito>::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9  
}  
1. Identifique las componentes de la misma.
2. Indique por qué es ambigua y corríjala.

Solución
------
1. N = {<número_entero>, <dígito> }  
T = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}  
S = <número_entero>  
P = {  
&nbsp;&nbsp;<número_entero>::=<dígito><numero_entero> | <numero_entero><dígito> | <dígito>  
&nbsp;&nbsp;<dígito>::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9  
}  

2. Es ambigua ya que en una de las componentes (en p), hay dos formas de representar un número entero: o bien un número entero y luego un dígito o bien un dígito y luego un número entero. La forma de solucionarlo es eliminando una de las formas ambiguas(en este caso yo voy a eliminar <numero_entero><dígito>, pero bien podría eliminarse <dígito><numero_entero> que sería exactamente lo mismo. La idea es que solo quede una manera de representar la recursión.).  
G = ( N, T, S, P)  
N = {<número_entero>, <dígito> }  
T = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}  
S = <número_entero>  
P = {  
&nbsp;&nbsp;<número_entero>::=<numero_entero><dígito> | <dígito>  
&nbsp;&nbsp;<dígito>::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9  
} 
