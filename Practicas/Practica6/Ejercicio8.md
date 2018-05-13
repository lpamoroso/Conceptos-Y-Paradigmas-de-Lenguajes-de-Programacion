# Ejercicio 8

a)Indique las diferencias entre los pasaje de subprogramas como parámetros deep y shallow.

* La ligadura shallow o superficial no es apropiada para lenguajes con estructuras de bloques ya que se puede acceder a ambientes que estáticamente no le eran 
visibles.
* Para lenguajes de alcance estático se utiliza la ligadura deepy se necesita que en el momento de la invocación a la unidad con parámetro subprograma además del puntero al código, se indique cual debe ser su ambiente de referencia, es decir un puntero al lugar de la cadena estática correspondiente.

b)Realice la pila estática y dinámica tanto con el pasaje de parámetros deep y shallow para el siguiente código.

```pascal
Program A
Var x:integer;
Var y: char;
Procedure B;
    Var h:integer;
    Begin
       h:=1+x;
       Write (y);
       C(D);
       Write (y);
    End;
Procedure C (Subrutina S);
    Var x:integer;
    Var y: char;
    Begin
      x:=3;
      y:= "b";
      x:=S(x,y)
      y:= "j";
      Write (x,y);
    End;
Function D (j:integer, k:char);
    Begin
      j:=j+x;
      k:=y;
      Write (k);
      Return j;
    End;
BEGIN
  x:=0;
  y:="a";
  B();
  Write (x,y);
END.
```
