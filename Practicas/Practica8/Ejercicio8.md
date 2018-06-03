# Ejercicio 8

Sean los siguientes, procedimientos de un programa escrito en CLU:

```CLU
Proc_1=proc(m:int)returns(int)
    signals(tipo1)
    .....
    if​ m=0 ​then​ signal tipo1
    Except
        when tipo1: write(“Se produjo un error de tipo1 en Proc_1”); signal tipo2;
        others: write(“Se produjo otro tipo de error en Proc_1”)
    end
    m:=m * 10
end Proc_1
Proc_2=proc()returns(int)
    z=0;
    While z>=0
        if​ z=0 ​ then​ Proc_1(z)
        Except
            when tipo2: write(“Se produjo un error de tipo2 en Proc_2”)
        end
    end while​;
    Except
        when tipo1: write(“Se produjo un error de tipo2 en Proc_2”)
    end
    .....
end Proc_2
Proc_ppal=proc()returns(int)
    .....
    Proc_2
    Except
        when tipo1: write(“Se produjo un error de tipo1 en Proc_ppal”)
    end
    .....
end Proc_ppal
```

1. Analizar el ejemplo y decir qué manejadores ejecuta y en qué valores quedan las variables. JUSTIFIQUE LA RESPUESTA.
2. Podría simular un efecto parecido en ADA? En caso de poder, explique cómo.

#

1. En Proc_ppal si surge una excepcion en ..... el programa aborta y finaliza su ejecucion. En Proc_2, si surge una excepcion de tipo1 en ....., se aborta el modulo y en la siguiente linea se maneja la excepcion correspondiente; si no fuera de tipo1, finaliza el modulo y continua la ejecucion en Proc_ppal. En Proc_1 hay declarado un signals de tipo1, lo cual hace posible que se pueda levantar una excepcion con un signal tipo1 y que esta sea manejada abajo del llamado al procedimiento. De no poder manejarse en ese except se busca estaticamente en el while, si no es posible falla el programa completo.

2. Se puede usando un declare. La idea es encapsular el procesamiento dentro del declare y aislar las excepciones(en el modulo que llama la excepcion), por lo que si surge una se mata el modulo (porque no hay forma de resolverla en el declare) y se busca una forma de manejarla en el modulo que la llamo que, convenientemente, va a tener la parte de su procesamiento involucrada de llamar a otro modulo dentro de otro declare. Dentro de ese declare, van a estar las excepciones que puede atender el modulo al que se invoca. Fuera del declare va a estar el resto del procesamiento. De esta forma, cuando surge una excepcion en Proc_1, no es manejada en el modulo en donde se produjo, termina dicho modulo y se busca una forma de resolverla en el modulo que llamo a ese modulo en donde se produjo la excepcion.

```ADA
Procedure Proc_1(in m: integer)
    tipo1: exception;
    .....
    declare
    begin
        if m=0 then raise tipo1
    end
    end
    exception
        when tipo1 => write(“Se produjo un error de tipo1 en Proc_ppal”)
    end
Procedure Proc_2;
    z: integer := 0;
    declare
    begin
    While z>=0
        if​ z=0 then​ Proc_1(z)
    end while​;
    exception
        when tipo2 => write(“Se produjo un error de tipo2 en Proc_2”)
        when tipo1 => write(“Se produjo un error de tipo2 en Proc_2”)
    end
    end
    .....
Procedure Proc_ppal;
    .....
    Proc_2
    .....
```
