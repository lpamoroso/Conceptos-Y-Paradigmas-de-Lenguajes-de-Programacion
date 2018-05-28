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

1.
