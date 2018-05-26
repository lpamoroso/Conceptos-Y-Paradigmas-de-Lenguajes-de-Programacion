# Ejercicio 1

1. ¿Qué es un sistema de tipos y cuál es su principal función?
2. Definir y contrastar las definiciones de un sistema de tipos fuerte y débil (probablemente en la bibliografía se encuentren dos definiciones posibles. Volcar ambas en la respuesta). Ejemplificar con al menos 2 lenguajes para cada uno de ellos y justificar.
3. Además de la clasificación anterior, también es posible caracterizar el tipado como estático o dinámico. ¿Qué significa esto? Ejemplificar con al menos 2 lenguajes para cada uno de ellos y justificar.  
#  
1. Conjunto de reglas que estructuran y organizan una colección de tipos. El objetivo del sistema de tipos es lograr que los programas sean tan seguros como sea posible.
2.
+ **Sistema de tipos fuerte**: Se dice que el sistema de tipos es  fuerte cuando especifica restricciones sobre cómo las operaciones que involucran valores de diferentes tipos pueden operarse. Ejemplo: Haskell, C++, etc.
+ **Sistema de tipos débil**: Se dice que el sistema de tipos es débil cuando el lenguaje no provee restricciones acerca de cómo las operaciones que involucran valores de diferentes tipos pueden operarse. Ejemplo: PERL, JavaScript, etc.
3.
+ **Tipado estático**: Se dice de un lenguaje de programación que usa un tipado estático cuando la comprobación de tipificación se realiza durante la compilación, y no durante la ejecución. Ejemplos de lenguajes que usan tipado estático son C, C++, Java y Haskell. Comparado con el tipado dinámico, el estático permite que los errores de tipificación sean detectados antes, y que la ejecución del programa sea más eficiente y segura.
+ **Tipado dinámico**: Se dice de un lenguaje de programación que usa un tipado dinámico cuando la comprobación de tipificación se realiza durante su ejecución en vez de durante la compilación. Ejemplos de lenguajes que usan tipado dinámico son Perl, Python y Lisp. Comparado con el tipado estático, o sistema de enlazado temprano, el tipado dinámico es más flexible (debido a las limitaciones teóricas de la decidibilidad de ciertos problemas de análisis de programas estáticos, que impiden el mismo nivel de flexibilidad que se consigue con el tipado estático), a pesar de ejecutarse más lentamente y ser más propensos a contener errores de programación.
