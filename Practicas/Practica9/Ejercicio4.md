# Ejercicio 4

¿Qué significa que un lenguaje utilice circuito corto o circuito largo para la evaluación de una expresión? De un ejemplo en el cual por un circuito dé error y no así el opuesto.

La evaluación de circuito corto denota la semántica de algunos operadores booleanos en algunos lenguajes de programación en los cuales el segundo argumento no se ejecuta o valúa si el primer argumento de la función AND evalúa y el resultado es falso, el valor total tiene que ser falso; y cuando el primer argumento de la función OR evalúa y el resultado es verdadero, el valor total tiene que ser verdadero.

Ejemplo de efectos colaterales:

```C
int denom = 0;
if (denom && num/denom) {
        ... // asegura que no se produzca un error al calcular num/denom es decir una división por cero
}
```

Considere el siguiente ejemplo usando lenguaje C:

```C
int a = 0;
if (a && myfunc(b)) {
    do_something();
}
```

En este ejemplo, la evaluación de circuito corto garantiza que myfunc(b) nunca será llamado. Esto es debido a que la evaluación de a es falso. Esta característica permite la programación de dos constructores. Inicialmente si se revisa la primera subexpresión, sin importar si es necesario un costo computacional y el proceso evaluado es falso, uno puede eliminar el costo computacional en el segundo argumento. Luego permite una construcción donde la primera expresión garantiza una condición sin la cual la segunda expresión pueda causar un error de ejecución run-time error. Ambos están ilustrados en el siguiente fragmento de código C donde una evaluación mínima previene una desferenciación a un apuntador a null y un desbordamiento de memoria.
