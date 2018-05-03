Ejercicio 1
======
¿Qué define la semántica?

Solución
------
Define un conjunto de reglas para dar significado a los programas sintacticamente validos. Hay dos tipos:
* Semántica estática
  + No esta relacionada con el significado del programa, sino con las formas válidas.
  + Las gramáticas sensibles al contexto (las de tipo G = N, T, S, P) resuelven los aspectos de este tipo de semántica.
* Semántica dinámica
  + Es la que describe el efecto de ejecutar las diferentes construcciones en el lenguaje de programación.
  + Su efecto se describe durante la ejecución del programa.
  + Los programas solo se pueden ejecutar si son correctos para la sintaxis y para la semántica estática.
  
 La evaluación de las reglas semánticas puede:
 * Generar código.
 * Insertar información en la tabla de símbolos.
 * Realizar el chequeo semántico.
 * Dar mensajes de error.
 * Etc.
