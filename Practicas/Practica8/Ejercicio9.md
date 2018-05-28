# Ejercicio 9

Indique diferencias y similitudes entre Python y Java con respecto al manejo de excepciones.  

## JAVA

Al igual que C++ las excepciones son objetos que pueden ser alcanzados y manejados por manejadores adicionados al bloque donde se produjo la excepción. Diferencias:
+ TODAS las excepciones que puedan ser alcanzadas explícitamente por la rutina y son chequeadas por el compilador, DEBEN ser listadas en la interface de la misma o ser manejadas por un manejador. La justificación de esta obligatoriedad es que el usuario de la rutina DEBE conocer qué excepciones puede alcanzar la misma.
+ Uso de FINALLY

```java
try
    bloque
catch (NombreExcepciónN)
    bloqueManejadorN
finally
    bloqueFinal
```

donde finally puede estar o no. Si está, la ejecución de su código se realiza cuando se termina la ejecución del bloque Try, se haya o no levantado una excepción. Salvo que el bloque Try haya levantado una excepción que no macheo con ningún manejador.

## Python

Se manejan a través de bloques try except

```python
>>> while True:
...
try:
... x = int(input("Por favor ingrese un número: "))
... break
...
...
except ValueError:
print("Oops! No era válido. Intente nuevamente...")
```

La declaración try funciona de la siguiente manera:

+ Primero, se ejecuta el bloque try (el código entre las declaración try y except).
+ Si no ocurre ninguna excepción, el bloque except se saltea y termina la ejecución de la declaración
try.
+ Si ocurre una excepción durante la ejecución del bloque try, el resto del bloque se saltea. Luego, si
su tipo coincide con la excepción nombrada luego de la palabra reservada except, se ejecuta el
bloque except, y la ejecución continúa luego de la declaración try.
+ Si ocurre una excepción que no coincide con la excepción nombrada en el except, esta se pasa a
declaraciones try de más afuera; si no se encuentra nada que la maneje, es una excepción no
manejada, y la ejecución se frena con un mensaje como los mostrados arriba.

¿Qué sucede cuando una excepción no encuentra un manejador en su bloque “try except”?
+ Busca estáticamente  
    *Analiza si ese try está contenido dentro de otro y si ese otro tiene un manejador para esa excepción.
    Sino...*
+ Busca dinámicamente  
    *Analiza quién lo llamó y busca allí*
+ Si no se encuentra un manejador, se corta el proceso y larga el mensaje standard de error
+ Levanta excepciones explícitamente con “raise”
