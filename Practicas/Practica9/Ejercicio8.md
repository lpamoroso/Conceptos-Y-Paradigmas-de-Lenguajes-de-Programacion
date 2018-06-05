# Ejercicio 8

Sea el siguiente código en Pascal:

```PASCAL
var puntos: integer;
begin
...
case puntos
1..5: write(“No puede continuar”);
10:write(“Trabajo terminado”)
end;
..
```

Analice, si esto mismo, con la sintaxis correspondiente, puede trasladarse así a los lenguajes ADA, C. ¿Provocaría error en algún caso? Diga cómo debería hacerse en cada lenguaje y explique el por qué. Codifíquelo.

```Ada
var puntos: integer;
begin
...
case puntos is
    when 1..5  => write(“No puede continuar”);
    when 10 => write(“Trabajo terminado”);
    when others => --no hace nada, pero hay que ponerlo.
end case;
...
```

En C no pude escribirlo dado que los cases del switch deben ser todos iguales y del mismo tipo que el de la variable del switch. Podría escribirse pero habría que desarmar el enumerativo y hacer un caso para cada valor(para el valor 1, 2, 3 así hasta 5) que hagan exactamente los mismo. Además, para cada caso, hay que incluir un break para terminar la ejecución luego de haber ejecutado el case deseado.
