# Paradigmas

1. ¿Qué es un paradigma?

Un paradigma de programación es un estilo de desarrollo de programas, un modelo para resolver problemas computacionales. Los lenguajes de programación, necesariamente, se encuadran en uno o varios paradigmas a la vez a partir del tipo de órdenes que permitan implementar, lo cual tiene una relación directa con su sintaxis.

2. ¿Cuáles son los principales paradigmas?

* **Imperativo**: sentencias  + secuencias de comandos
* **Declarativo**: los programas describen los resultados esperados sin listar explícitamente los pasos a llevar a cabo para alcanzarlos.
* **Lógico**: Es un paradigma en el cual los programas son una serie de aserciones lógicas. El conocimiento se representa a través de **reglas** y **hechos**. Los objetos son representados por **términos**, los cuales contienen constantes y variables. PROLOG es el lenguaje lógico más utilizado.  
	Elementos  
	La sintáxis básica es el **término**. Éstos contienen:
	+ **Constantes**: son elementos determinados. La constantes son string de letras en minúsculas(representan objetos atómicos) o string de dígitos(representan números). Ejemplo: *humano(juan)*, en donde *juan* representa la constante.
	+ **Variables**: elementos indeterminados que pueden sustituirse por cualquier otro. Los nombres de las variables comienzan con mayúsculas y pueden incluir números. Ejemplo: *humano(X)*, la *X* representa la variable y puede ser sustituída por constantes como: juan, pepe, etc.
	
	Además de los términos, existen los **términos compuestos**. Éstos consisten en un functor seguido de un número fijo de argumentos encerrados entre paréntesis, los cuales son a su vez términos. Denominaremos *aridad* al número de argumentos y *estructura* a un término compuesto cuyos argumentos no son variables. Ejemplos: padre->constante; Longitud->variable; tamaño(4,5)->estructura. A su vez, la aridad de tamaño es 2.  
	También existen las listas. La constante *[]* representa una lista vacía. El functor *.* construye una lista de un elemento y una lista. Ejemplo: .(alpha,[]), representa una lista que contiene un único elemento que es alpha. Otra manera de representar la lista es usando *[]* en lugar de *.()*. Volviendo al ejemplo anterior: [alpha,[]]. También puede utilizarse el símbolo *|* en lugar de *,*. En nuestro ejemplo: [alpha|[]]. La notación general para denotar una lista es: [X|Y] donde *X* es el elemento cabeza de la lista e *Y* es una lista que representa la cola de la lista que se está modelando.  
	
	Cláusulas de Horn
	
	
	
* **Funcional o aplicativo**: basado en el uso de funciones. Muy popular en la resolución de problemas de inteligencia artificial, matemática, lógica, procesamiento paralelo, etc.  
	Características:
	+ Define un conjunto de datos.
	+ Provee un conjunto de funciones primitivas.
	+ Provee un conjunto de formas funcionales.
	+ Requiere de un operador de aplicación.
	+ Semántica basada en valores.
	+ Transparencia referencial.
	+ Regla de mapeo basada en combinación o composición.
	+ Las funciones de primer orden.
	
	Algunas ventajas son:
	+ Vista uniforme de programa y función.
	+ Tratamiento de funciones como datos.
	+ Liberación de efectos colaterales.
	+ Manejo automático de memoria.
	
	La desventaja es la ineficiencia de ejecución.  
	El **valor** más importante en la programación funcional es el de una **función**. Las funciones son tratadas como valores, pueden ser pasadas como parámetros, retornar resultados, etc.  
	Se debe distinguir entre el **valor** y la **definición** de una función. Existen muchas maneras de **definir** una misma función, pero siempre dará el mismo valor, ejemplo: *DOBLE X = X + X* y *DOBLE’ X= 2 * X*. Denotan la misma función pero son dos formas distintas de definirlas.  
	Tipo de una función
	+ Puede estar definida explícitamente dentro del **script**, por ejemplo: cuadrado::numnum cuadrado x= x + x.
	+ Puede **deducirse/inferirse** el tipo de una función.
	
	Expresiones y valores  
	Una expresión es su **valor**. El valor de una expresión depende **únicamente** de los valores de las subexpresiones que la componen. Las expresiones también pueden contener **variables**(valores desconocidos). Las expresiones cumplen con la propiedad de "**transparecia referencial**": dos expresiones sintácticamente iguales darán el mismo valor, porque no existen **efectos laterales**. Algunas expresiones pueden **no** llegar a reducirse del todo, ejemplo: 1/0. A esas expresiones se las denominan **canónicas**, pero se les asigna un **valor indefinido** y corresponde al símbolo bottom(^). Por lo tanto toda **expresión** siempre denota un **valor**.  

	**IMPORTANTE**: La noción de variable es la de “variable matemática”, no la de celda de memoria. Diferentes ocurrencias del mismo nombre hacen referencia al mismo valor desconocido.  
	
	Evaluación de las expresiones  
	La forma de evaluar es a través de un mecanismo de **reducción o simplificación**. Lo importante es que, de nuevo, no importa la forma de evaluarla, **el resultado final siempre será el mismo**. Dos formas de reducción:
	+ **Orden aplicativo**: aunque no lo necesite, siempre evalúa los argumentos.
	+ **Orden normal**: no calcula más de lo necesario. La expresión **no** es evaluada hasta que su valor se necesite. Una expresión compartida **no** es evaluada más de una vez.
	
	Tipos de dato  
	Hay dos tipos:
	+	**Básicos**: son los primitivos. Ejemplo: NUM (incluye INT y FLOAT) (Números), BOOL(Valores de verdad), CHAR(Caracteres).
	+ **Derivados**: se construyen de otros tipos. Ejemplo: (num,char) Tipo de pares de valores, (num -> char) Tipo de una función.
	
	**Toda función tiene asociado un tipo.** Sin embargo, algunas veces no es tan simple deducirlo. Es el caso de las **expresiones de tipo polimórficas**.
	
	Currificación
	Mecanismo que reemplaza argumentos estructurados por argumentos más simples.
	
	Cálculo Lambda
	Es un modelo de computación para definir funciones. Se utiliza para entender los elementos de la programación funcional y la semántica subyacente, independientemente de los detalles sintácticos de un lenguaje de programación en particular. Las expresiones del cálculo Lambda pueden ser de 3 clases:
	+ Un simple identificador o una constante. Ej: x, 3.
	+ Una definición de una función. Ej: λ x.x+1.
	+ Una aplicación de una función. La forma es (e1 e2), dónde se lee e1 se aplica a e2.
* **Orientado a Objetos**: métodos + mensajes.
* **Dirigido por eventos**: el flujo del programa está determinado por sucesos externos(por ejemplo, una acción del usuario).
* **Orientado a aspectos**: apunta a dividir el programa en módulos independientes, cada uno con un comportamiento y responsabilidad bien definido.

