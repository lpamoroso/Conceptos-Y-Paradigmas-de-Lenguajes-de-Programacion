# Ejercicio 3

¿Una expresión de asignación puede producir efectos laterales que afecten al resultado final, dependiendo de cómo se evalúe? De ejemplos.

Sí. Una expresión de asignación puede tener diferentes resultados dependiendo de cómo se evalúe(de izquierda hacia derecha o de derecha hacia izquierda). Por ejemplo:
```PASCAL
z:= 1;
x := z + F(z);
Function F(var z: integer): integer
begin
       z := z + 1;
end
```
Si se evalúa de izquierda a derecha se obtiene x = 3 y si se evalúa de derecha a izquierda se obtiene 4.
