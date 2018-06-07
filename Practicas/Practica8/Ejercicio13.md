# Ejercicio 13

Dado el siguiente código en Ada. Marque con una cruz sólo los caminos de ejecución correctos en los casos en que se produzca o levante una excepción.
```Ada
Program Main
var x,y,i:integer;
e,e2:exception
Procedure A
  var y,b:integer;
  e:exception;
Begin
  x=x=+1;
  y=0;
  b=x+i+3;
  B();
  (6) Exception when e Begin
    x:=x + 5; raise;
    End;
End;
Procedure B
  var z:integer;
Begin
  z=3;
  raise e; (7)
  (4) Exception when e Begin
    x:=x + 1; raise;
    End;
  (9) when e2 Begin
    x:=x + 6;
    End;
  (5) when others Begin
    x:=x + 1;
    End;
End;
Procedure C
Begin
  If (x=1) then begin
    raise e2; (8)
  end;
  else A();
End;
BEGIN //MAIN
  x=1; y=1; i=2;
  C();
  write(x);
  (1) Exception when e Begin
    x:=x + 5;
    End;
  (2) when e2 Begin
    x:=x + 6;
    End;
  (3) when others Begin
    x:=x + 7;
    End;
END.
```

<table>
  <tr>
    <td>
    En (7) se levanta e y se maneja en 4, luego se relanza la excepción que es manejada en (6) y termina manejándose nuevamente en (1)
    <b>Falso.</b>
    </td>
    <td>
    En(7) se levanta e y se maneja en 4, luego se relanza la excepción que es manejada en(1) porque e pertenece a main.
    <b>Verdadero.</b>
    </td>
    <td>
    En(8) se levanta e2 y se maneja en 4, luego se relanza la excepción que es manejada en (1) porque e pertenece a main.
    <b>Falso.</b>
    </td>
  </tr>
  <tr>
    <td>
    En (7) se levanta e y se maneja en 4, luego se vuelve a levantar la excepción de forma anónima por lo que B termina y se busca el manejador en A para manejarse finalmente en (1) de Main porque C y A no tiene manejadores definidos para esa variable.
    <b>Falso.</b>
    </td>
    <td>
    En (7) se levanta e y se maneja en 4, luego se relanza la excepción que es manejada en (3) porque e pertenece a main pero pierde el alcance en A.
    <b>Falso.</b>
    </td>
    <td>
    En (8) se levanta e2 y se maneja en 2, y el programa termina.
    <b>Verdadero.</b>
  </tr>
</table>
