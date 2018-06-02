# Ejercicio 9

¿Qué diferencia existe entre el generador YIELD de Python y el return de una función? De un ejemplo donde sería útil utilizarlo.

En ambos casos obtenemos la lista de productos desde nuestro repositorio, pero con una gran diferencia: con el return obtenemos la lista completa antes de devolverla, mientras que con el YIELD los elementos se van obteniendo a medida que lo necesite quien nos llame. Esto es importante por varios motivos:
+ La mayoría de las veces obtener toda la lista a priori será un desperdicio. Imagina que hay miles de registros y el método que nos llama sólo ha de acceder a los primeros.
+ Obtener una lista muy larga de valores completamente consume mucho tiempo. Si estamos mostrando un listado a un usuario, éste deberá esperar a que se obtenga todos los elementos antes de ver nada… ¡Incluso aunque en la UI paginemos el resultado!
En cualquier caso, siempre podemos materializar la lista completa antes de utilizarla.
En resumen, yield nos ofrece una forma sencilla de trabajar óptimamente con listas de elementos ahorrándonos los detalles más tediosos de implementar los interfaces corespondientes, ya que el compilador lo hace por nosotros
