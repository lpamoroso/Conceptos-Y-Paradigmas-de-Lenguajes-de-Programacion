# Subinciso B del inciso II del punto 2.

## Cadena Dinámica por valor

|*1|PR|
|:------:|:------:|
|  |LE|
|  |LD|
|  |j = 3|
|  |m = 2|
|  |i = 1|
|  |Proc. Recibe(x:integer; y:integer)|
|  |Proc. Dos()|
|  |VR|
|*2|PR|
|*1|LE|
|*1|LD|
|  |m = ~~5~~9|
|  |VR|
|*3|PR|
|*1|LE|
|*2|LD|
|  |x = ~~1~~5|
|  |y = ~~3~~8|
|  |VR|

write (x, y, i, j, m); (procedure recibe) --> imprime 5, 8, 1, 3, 9.  
write (i, j, m); (procedure dos) --> imprime 1, 3, 9.  
write (i, j, m); (procedure main) --> imprime 1, 3, 2.
