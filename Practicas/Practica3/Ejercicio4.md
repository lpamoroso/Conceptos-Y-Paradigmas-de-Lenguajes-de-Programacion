Ejercicio 4
======
Explique claramente cuál es la diferencia entre un error sintáctico y una semántico. Ejemplifique cada caso.

Solución
------
Un error sintáctico es aquel que ocurre cuando una sentencia no está escrita de la forma que el lenguaje la acepta. El formato puede estar especificado en documentos BNF/EBNF. Ejemplo: x int = 9;  
Un error semántico ocurre cuando, si bien la sintaxis es correcta, hay un problema en el significado. Hay errores semánticos que se detectan en compilación(semántica estática) y otros durante la ejecución(semántica dinámica). Ejemplo: int x = "coso";
