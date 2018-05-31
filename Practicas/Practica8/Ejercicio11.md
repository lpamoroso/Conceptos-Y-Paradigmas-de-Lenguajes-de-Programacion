# Ejercicio 11

Sea el siguiente programa escrito en ADA:

```ADA
Procedure Principal;
    x:exception;
    y:integer;
    b:boolean;
Procedure Prueba1 (out m:integer);
    begin
    m:=20;
    if (b=true) then raise X;
    m:=m + 2;
    end;
    Procedure Prueba2;
    a:int:=0; b:=4/a;
    begin
        y:=y+8;
    exception
    when constraint-error => y:=y+10;
end;
begin
    Read(b);
    y:=1;
    Prueba1(y);
    Prueba2;
    write(y);
    exception
    when constraint-error =>
    begin
        y:=y+4;
        write(Y);
    end;
    when X =>
    begin
        y:= y*30;
        write(Y);
    end;
end;
```

1. Indique el camino de ejecución.
2. Agregar el uso de una excepción anónima

#

1.
