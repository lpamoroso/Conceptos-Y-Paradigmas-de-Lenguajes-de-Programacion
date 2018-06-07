# Ejercicio 7

Sea el siguiente programa escrito en pascal:

```pascal
Program​ Principal;
    var x:int; b1,b2:boolean;
    Procedure​ P (b1:boolean);
        var x:int;
        Procedure​ Manejador1
            begin
                x:=x + 1;
            end;
        begin
            x:=1;
            if b1=true then Manejador1;
            x:=x+4;
        end;
    Procedure​ Manejador2;
        begin
            x:=x * 100;
        end;
    Begin
        x:=4;
        b:=true;
        b1:=false;
        if b1=false then Manejador2;
        P(b);
        write (x);
    End.
```

1. Implemente este ejercicio en PL/1 utilizando manejo de excepciones
2. ¿Podría implementarlo en ADA utilizando manejo de excepciones? En caso afirmativo, realícelo.

#

1.
```PL/1
Program​ Principal;
    var x:int; b1,b2:boolean;
    Procedure​ P (b1:boolean);
        var x:int;
        ON CONDITION(Manejador1)
            begin
                x:=x + 1;
            end;
        begin
            x:=1;
            if b1=true then Signal condition(Manejador1);
            x:=x+4;
        end;
    ON CONDITION(Manejador2)
        begin
            x:=x * 100;
        end;
    Begin
        x:=4;
        b:=true;
        b1:=false;
        if b1=false then Signal condition(Manejador2);
        P();
        write (x);
    End.
```

2. Si, podría hacerlo:
```ADA
Program​ Principal;
    var x:int; b1,b2:boolean;
    Manejador1: Exception;
Procedure​ P (b1:boolean);
    var x:int;
    Manejador1: Exception;
    begin
        x:=1;
        if b1=true then Manejador1;
        x:=x+4;
        Exception
            when Manejador1 => x:=x + 1;
    end;
Begin
    x:=4;
    b:=true;
    b1:=false;
    if b1=false then Manejador2;
    P(b);
    write (x);
    Exception
        when Manejador2 => x:=x * 100;
End.
```
