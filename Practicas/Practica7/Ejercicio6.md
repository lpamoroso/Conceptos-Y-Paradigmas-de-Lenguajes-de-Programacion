# Ejercicio 6

1. ¿Qué características debe cumplir una unidad para que sea un TAD?
2. Dar algunos ejemplos de TAD en lenguajes tales como ADA, Java, Python, entre otros.

#

1. Un TAD está caracterizado por un conjunto de operaciones (funciones) al cual se denomina usualmente como interfaz pública y representa el comportamiento del TAD; mientras que la implementación como la parte privada del TAD está oculta al programa cliente que lo usa. Todos los lenguajes de alto nivel tienen predefinidos TAD; que son los tipos denominados simples y las estructuras predefinidas, y estos tienen sus interfaces públicas que incluyen las operaciones como la +, -, *, etc. No se necesita conocer como actúan tales operadores sobre la representación interna de los tipos definidos, que además, suele ser una implementación bastante dependiente de la máquina sobre la que trabaje el compilador. Lo interesante es que los lenguajes actuales nos van a permitir ampliar los TAD predefinidos con otros que serán definidos por el propio programador para adecuar así los tipos de datos a las necesidades de los programas.  
Los TAD que nos van a interesar de ahora en adelante son aquellos que reflejen cierto comportamiento organizando cierta variedad de datos estructuradamente. A esta forma estructurada de almacenar los datos será a la que nos refiramos para caracterizar cada TAD.
Los TAD que tienen informaciones simples pero dependientes de un comportamiento estructural serán llamados políticos y aquellos TAD simples, como son los tipos predefinidos donde la información no es relacionada mediante ninguna estructura y no admiten más que un valor en cada momento serán denominados TAD monolíticos.  
Nótese que cuando hablemos de un TAD no haremos ninguna alusión al tipo de los elementos sino tan solo a la forma en que están dispuestos estos elementos. Solo nos interesa la estructura que soporta la información y sus operaciones. Para determinar el comportamiento estructural basta con observar la conducta que seguirán los datos.  
Caractericemos entonces los TAD. Un TAD tendrá una parte que será invisible al usuario la cual hay que proteger y que se puede decir que es irrelevante para el uso del usuario y está constituida tanto por la maquinaria algorítmica que implemente la semántica de las operaciones como por los datos que sirvan de enlace entre los elementos del TAD, es decir, información interna necesaria para la implementación que se esté haciendo para ese comportamiento del TAD. Resumiendo podemos decir, que tanto la implementación de las operaciones como los elementos internos del TAD serán privados al acceso externo y ocultos a cualquier otro nivel.  
Un TAD representa una abstracción:

* Se destacan los detalles (normalmente pocos) de la especificación (el qué).
* Se ocultan los detalles (casi siempre numerosos) de la implementación (el cómo).

2. Algunos ejemplos del uso de TAD en programación son:

+ Conjuntos: implementación de conjuntos con sus operaciones básicas (unión, intersección y diferencia), operaciones de inserción, borrado, búsqueda, etc.
+ Árboles Binarios de Búsqueda: Implementación de árboles de elementos, utilizados para la representación interna de datos complejos. Aunque siempre se los toma como un TAD separado son parte de la familia de los grafos.
+ Pilas y Colas: Implementación de los algoritmos FIFO y LIFO.
+ Grafos: Implementación de grafos; una serie de vértices unidos mediante una serie de arcos o aristas.
