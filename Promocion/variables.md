# Variables

1. ¿Qué es una ligadura?

Los programas trabajan con entidades(variables, rutinas, etc). Todas las entidades tienen atributos y éstos tienen que establecerse antes de poder usar la entidad. Una ligadura es la asociación entre la entidad y el atributo. Éstas tienen un momento y una estabilidad. El momento indica cuándo es seteada la ligadura y la estabilidad indica que si, una vez establecida, puede variar o no.  
Con respecto al momento, podemos clasificar a las ligaduras en dos tipos:
* **Ligaduras estáticas**: se establecen antes de la ejecución y no se pueden cambiar. El termino estático referencia al momento del binding y a su estabilidad.
* **Ligaduras dinámicas**: si se establecen en el momento de la ejecución y pueden cambiar de acuerdo a alguna regla específica del lenguaje.

2. ¿Qué es una variable?

Es un espacio reservado en la memoria principal, identificado por una dirección. El contenido de una celda es una representación codificada de un valor. Toda variable posee los siguientes atributos:
* **Nombre**: string de caracteres que se usa para referenciar a la variable(identificador).
* **Alcance**: es el rango de instrucciones en el que se conoce el nombre(visibilidad). Las instrucciones del programa pueden manipular una variable a través de su nombre dentro de su alcance. Esto significa que, si bien una variable teoricamente tendría alcance en tal rango de instrucciones, podría no ser así en todos los casos. Un ejemplo es el enmascaramiento de variables. Lo que ocurre en este caso es que dentro de dos funciones distintas, por ejemplo, hay dos variables que tienen el mismo nombre por lo que solo una puede ser referenciada con tal identificador en un momento determinado. Paso a explayarme aún más: si yo tengo una función A y una función B, y hay dos variables, una global y otra local a la función B que llevan el mismo nombre y ocurre que función A llama a función B entonces, si bien la variable A resulta alcanzable dentro de la función B, resulta que la variable B enmascara a A, por lo que solo es alcanzable B durante el transcurso de la función.  
Hay dos tipos de alcance:
	+ **Alcance estático**: llamado también alcance léxico, define el alcance en términos de la estructura léxica del programa. Puede ligarse estáticamente a una declaración(explícita o implícita) examinando el texto del programa, sin necesidad de ejecutarlo. La mayoría de los lenguajes adoptan reglas de ligadura de alcance estático.
	+ **Alcance dinámico**: define el alcance del nombre de la variable en términos de la ejecución del programa. Cada declaración de variable extiende su efecto sobre todas las instrucciones ejecutadas posteriormente, hasta que una nueva declaración para una variable con el mismo nombre es encontrado durante la ejecución.
	Con respecto a lo anterior ¿Cuál conviene implementar?  
	Nuevamente, la respuesta es depende lo que se busque. A simple vista, si bien las reglas dinámicas son mas fáciles de implementar, son menos claras en cuanto a disciplina de programación y por lo tanto el código se hacen mas difícil de leer.

	Otra clasificación del alcance es la que sigue:
	+ **Local**: son todas la referencias que se han creado dentro del programa o subprograma.
	+ **No Local**: son todas las referencias que se utilizan dentro del subprograma pero que no han sido creadas en él.
	+ **Global**: Son todas las referencias creadas en  el programa principal.
* **Tipo**: según éste los valores que pueda tomar y las operaciones en que pueda participar.
* **L-value**: es el lugar de memoria asociado con la variable(tiempo de vida).
* **R-value**: es el valor codificado almacenado en la ubicación de la variable.

3. Alias

Dos variables son alias si comparten el mismo objeto de dato en el mismo ambiente de referencia. El uso de alias pude llevar a programas de difícil lectura y a errores dado que se puede modificar(de forma colateral, por lo general) una variable no local.

4. Sobrecarga

Un nombre esta sobrecargado si, en un momento, referencia mas de una entidad y hay suficiente información para permitir establecer la ligadura unívocamente.

Tip para diferenciar alias de sobrecarga
* Alias: distintos nombres apuntan a una entidad.
* Sobrecarga: un nombre apunta a distintas entidades.
