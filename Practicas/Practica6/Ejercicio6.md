# Ejercicio 6

Indique, con un ejemplo, el comportamiento del parámetro por nombre (en el parámetro formal) para los siguientes casos de parámetros reales:
* Un valor entero.
```
Procedure A();
var m:integer;
a: array[1..10] of integer;
Procedure B(nombre j:integer);
  begin
    j:=j+5; 
    m:=m+1;
    j:= j+ m; 
    write (j,m);
  end;
begin
  for m=1 to 10 begin    a[m]=m;   end; 
  m:=4;      B(
  a(m)
  );
  write (m);
end;
```
* Una constante.
```
Procedure A();
var m:integer;
a: array[1..10] of integer;
Procedure B(nombre j:integer);
  begin
    j:=j+5; 
    m:=m+1;
    j:= j+ m; 
    write (j,m);
  end;
begin
  for m=1 to 10 begin    a[m]=m;   end; 
  m:=4;      B(
  a(m)
  );
  write (m);
end;
```
* Un elemento de un arreglo.
```
Procedure A();
var m:integer;
a: array[1..10] of integer;
Procedure B(nombre j:integer);
  begin
    j:=j+5; 
    m:=m+1;
    j:= j+ m; 
    write (j,m);
  end;
begin
  for m=1 to 10 begin    a[m]=m;   end; 
  m:=4;      B(
  a(m)
  );
  write (m);
end;
```
* Una expresión.
```
Procedure A();
var m:integer;
a: array[1..10] of integer;
Procedure B(nombre j:integer);
  begin
    j:=j+5; 
    m:=m+1;
    j:= j+ m; 
    write (j,m);
  end;
begin
  for m=1 to 10 begin    a[m]=m;   end; 
  m:=4;      B(
  a(m)
  );
  write (m);
end;
```
¿Qué sucede en cada caso?

* Un único valor se comporta exactamente igual que el pasaje 
por referencia.
* Si es una constante es equivalente a por valor.
* Si es un elemento de un arreglo puede cambiar el suscripto 
entre las distintas referencias
* Si es una expresión se evalúa cada vez
