# Ejercicio 6

Sea el siguiente programa escrito en Pascal

```Pascal
...
Procedure Manejador;
    Begin ... end;
Procedure P(X:Proc);
    begin
    ....
    if Error then X;
    ....
    end;
Procedure A;
    begin
    ....
    P(Manejador);
    ....
    end;
    ....
```

¿Qué modelo de manejo de excepciones está simulando? ¿Qué necesitaría el programa para que encuadre con los lenguajes que no utilizan este modelo? Justifique la respuesta.  

Esta usando un manejo de excepciones por reasunción ya que una vez que se ejecuta la excepción sigue con la ejecución normalmente.
Si lo que se quisiera es que maneje la excepción por terminación, entonces si Error es true debe terminar la ejecución.
