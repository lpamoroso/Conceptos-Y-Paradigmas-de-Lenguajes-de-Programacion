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

1. El Read(b) indica que el usuario determina el valor de verdad de dicha variable, por lo tanto tenemos dos caminos de ejecucion a evaluar.
En principio, el camino de ejecucion no difiere en nada ya que los valores de las variables son iguales en los dos casos. Se envia y a Prueba1, pero como el parametro que recibe dicha funcion es de tipo OUT, esto no tiene mucho sentido. En dicha funcion, se le asigna a m(el parametro y que pasamos desde el main) 20 y aca es cuando la cosa puede variar.
Si b es true, entonces va a entrar en el if y va a levantar la excepcion X. Ante este escenario se va a intentar manejar la excepcion localmente pero va a ser imposible dado que no hay un manejador definido para dicho error. Ada utiliza la propagacion dinamica, por lo que ese modulo va a finalizar y se buscara una forma de resolver la excepcion en el main. En este caso, es posible resolverla, por lo que se le asigna 500 a y y se imprime dicho valor y se continua la ejecucion en Main. Luego de Prueba 1 se ejecuta Prueba2 y ocurre un contraint_error dado que se intenta asigna 4/0 a b. En este caso, se procede a abortar el modulo y a intentar manejar la excepcion en el Main. En este caso, la excepcion es manejada exitosamente y se le asigna 504 a y y se imprime dicho valor. Luego se continua la ejecucion en Main y se imprime el valor de y y termina el programa.
Por el contrario, si b es false, entonces no entra al if y se le suma 2 a m y finaliza el modulo, dejando a y con 22. Luego se ejecuta Prueba2 y ocurre lo mismo que se b fuera true, solo que, en este caso, cuando se resuelva la excepcion y queda con 26 y se imprime dicho valor. Cuando se retoma la ejecucion en Main, imprime 26.

<<<<<<< HEAD
2.
```ADA
Procedure Principal;
    x:exception;
    y:integer;
    b:boolean;
Procedure Prueba1 (out m:integer);
    x: exception;
=======
2.  
    ```ADA
    Procedure Principal;
        x:exception;
        y:integer;
        b:boolean;
    Procedure Prueba1 (out m:integer);
        x: exception;
        begin
            m:=20;
            if (b=true) then raise X;
            m:=m + 2;
            exception
                when x => raise x
        end;
    Procedure Prueba2;
        a:int:=0; b:=4/a;
        begin
            y:=y+8;
            exception
                when constraint-error => y:=y+10;
        end;
>>>>>>> 839ba0aeb10869680191c321ac57e01fe5577afc
    begin
        m:=20;
        if (b=true) then raise X;
        m:=m + 2;
        exception
            when x => raise x
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

En este caso, cuando la excepcion x es levantada en prueba 1 se resuelve en ese mismo modulo y se relevanta y finaliza el modulo Prueba1. En ese momento la excepcion ya es anonima dado que el modulo que contenia la declaracion de la excepcion x ya no existe y no es compatible con otro modulo que tenga declarada esa excepcion ya que, a pesar de llamarse igual, son distintas entre si por lo que cuando intenta resolverse en Main no puede, ya que hay otra excepcion x declarada alli.
