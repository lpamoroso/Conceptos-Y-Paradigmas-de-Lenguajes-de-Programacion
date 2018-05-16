# Ejercicio 4

Sea el siguiente programa escrito en Pascal-like

```pascal
Procedure Main;
var j, m, i: integer;
Procedure Recibe (x:integer; y:integer);
  begin
  m:= m + 1 + y;
  x:=i + x + j;
  y:=m - 1;
  write (x, y, i, j, m);
  end;
Procedure Dos;
  var m:integer;
  begin
  m:= 5;
  Recibe(i, j);
  write (i, j, m);
  end;
begin
  m:= 2;
  i:=1; j:=3;
  Dos;
  write (i, j, m);
end.
```

1. Arme el árbol de anidamiento sintáctico y el registro de activación de cada una de las unidades.

2. Decir qué imprime el programa suponiendo que para todas las variables que se pasan el pasaje de parámetros es por: (Deberá hacer la pila estática y dinámica para cada caso)
    1. Referencia.
    2. Valor.
    3. Valor-Resultado.
    4. Nombre.
    5. Resultado.
    
3. ¿Existió algún caso que no pudo realizarlo porque saltó algún tipo de error? Diga cuál y por qué.

4. ¿Dará el mismo resultado si se trata de un lenguaje que sigue la cadena dinámica? Justifique la respuesta realizando las pilas de activación.

## Solución

1. Encontrar herramienta para crear árbol.

### Cadena dinámica

|*1|PR|
|:------:|:------:|
|  |LE|
|  |LD|
|  |j = ~~3~~8|||
|  |m = 2|||
|  |i = ~~1~~5|||
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
|  |  |
|  |VR|

write (x, y, i, j, m); (procedure recibe) --> imprime 5, 8, 5, 8, 9.
write (i, j, m); (procedure dos) --> imprime 5, 8, 9.
write (i, j, m); (procedure main) --> imprime 5, 8, 2.
