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

2.

```ADA
Procedure Proc_1(in m: integer)
    tipo1: exception;
    .....
    declare
    begin
        if m=0 then raise tipo1
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
