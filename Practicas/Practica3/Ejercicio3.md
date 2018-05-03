Ejercicio 3
======
Con respecto al punto anterior ¿Es lo mismo compilar un programa que interpretarlo? Justifique su respuesta mostrando las diferencias básicas, ventajas y desventajas de cada uno.

Solución
------
Diferencias básicas:

| Intérprete    | Compilador    |
|:-------------:|:-------------:|
| Ejecuta el programa de entrada directamente siguiendo el orden **lógico** de ejecución | Produce un programa equivalente en lenguaje objeto siguiendo el orden **físico** de las sentencias |

Ventajas y desventajas:

| Intérprete    | Compilador    |
|:-------------:|:-------------:|
| Ocupa mejos espacio | Una sentencia puede ocupar cientos de lineas de máquina |
| Mas lento en ejecución | Mas rápido desde el punto de vista del hardware |
| Las sentencias del código fuente pueden ser relacionadas directamente con las que se están ejecutando | Cualquier referencia al código fuente se pierde en el código objeto |
| Por cada sentencia se realiza el proceso de decodificación para determinar las operaciones a ejecutar y sus operandos | No repite lazos, la decodificación se realiza una sola vez |
