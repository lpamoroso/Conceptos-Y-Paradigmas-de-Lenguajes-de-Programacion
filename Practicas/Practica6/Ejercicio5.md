# Ejercicio 5

Suponiendo que se está ejecutando un programa con el siguiente registro de activación en memoria y se llama al procedimiento rutina(iter,vec,a). Determine el tipo de parámetro que se deben utilizar en el llamado para que los resultados sean los siguientes:

1. (4,6,7),(4,6,7), 2, 2
2. (3,5,6),(4,6,7), 2, 2
3. (3,5,6),(5,5,6), 0, -1

|PR|
|:------:|
|LE|
|LD|
|Iter = true|
|Vec:[3,5,6]|
|a: -1|
|Rutina()|
|VR|

```
......
procedure rutina(tipoParam iteracion,tipoParam vector,tipoParam vit):
  while iteracion begin
  vit = a+1
  vector[vit] = vector[vit]+1
  iteracion = (vector[vit] mod 2)==0
  end
  print vec
  print vector
  print vit
  print a
.....
rutina(iter,vec,a)
```

1. Por valor, referencia, valor-resultado o por nombre; por referencia, por valor-resultado o por nombre; por referencia, por valor-resultado o por nombre.
2. Por valor, referencia, valor-resultado o por nombre; por valor; por referencia, por valor-resultado o por nombre.
3. Por valor, referencia, valor-resultado o por nombre; por valor; por valor.
