# Semántica

1. ¿Qué es la semántica?

Es un conjunto de reglas para dar significado a los programas sintácticamente válidos. Describe el significado de los símbolos, palabras y frases de un lenguaje ya sea lenguaje natural o lenguaje informático. Esto implica que para que un programa sea semánticamente válido debe serlo también sintácticamente. No así, el que sea sintácticamente válido implica necesariamente también lo sea semánticamente.

2. ¿Cuál es la utilidad de definir y conocer la semántica de un lenguaje? ¿Quiénes se benefician?

La definición de la semántica de un lenguaje de programación proporcionan mecanismos para que una persona o una computadora pueda decir, sinedo el programa ya válido, lo que significa. Esto, a primera vista, implicaría que solo el programador se beneficia de esto. Lo cierto es que también estas reglas sirven para el desarrollo de compiladores e intérpretes, por lo que, si no se hiciera tanta énfasis como se hace, el desarrollo de éstos no sería posible.

3. ¿Qué tipos de semánticas existen?

Hay dos tipos:
* **Semántica estática**: no está relacionado con el significado del programa, está relacionado con las formas validas. Se la llama así porque el análisis para el chequeo puede hacerse durante la compilación o el interpretado. Generalmente las gramáticas sensibles al contexto resuelven los aspectos de la semántica estática.
* **Semántica dinámica**: es la que describe el efecto de ejecutar las diferentes construcciones en el lenguaje de programación. Su efecto se describe durante la ejecución del programa. Los programas solo se pueden ejecutar si son correctos para la sintáxis y para la semántica estática.

4. ¿Cómo se describe la semántica?

Algunas soluciones son:
* **Semántica axiomática**: considera al programa como una máquina de estados. Los constructores de un lenguajes de programación se formalizan describiendo como su ejecución provoca un cambio de estado.
* **Semántica denotacional**: cada frase en el lenguaje es interpretada como una denotación. Tales denotaciones a menudo son objetos matemáticos que habitan espacios matemáticos, pero no es un requerimiento que éstas deban serlo. Como una necesidad práctica, las denotaciones se describen usando alguna forma de notación matemática, la cual en turno puede ser formalizada como un metalenguaje denotativo.
* **Semántica operacional**: el significado de un programa se describe mediante otro lenguaje de bajo nivel implementado sobre una máquina abstracta. Los cambios que se producen en el estado de la máquina cuando se ejecuta una sentencia del lenguaje de programación definen su significado
