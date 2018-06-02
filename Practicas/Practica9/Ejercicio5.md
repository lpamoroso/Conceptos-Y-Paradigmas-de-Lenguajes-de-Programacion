# Ejercicio 5

¿Qué regla define Delphi, Ada y C para la asociación del else con el if correspondiente? ¿Cómo lo maneja Python?

+ Delphi

    ```Delphi
    If Condición(es) then
        Begin
           {Bloque de Instrucciones};
        End
    Else
        Begin
           {Bloque de Instrucciones};
        End
    ```

    Para unir dos o más condiciones se pueden valer de los operadores AND, OR y para negar una condición se usa el operador NOT. La única diferencia en los operadores de Igualdad es ':=' no es lo mismo que '=', el primero es para asignar un valor a una variable y el segundo compara dos objetos, valores, números etc.

+ Ada

    Un if_statement selecciona para ejecutar como mucho una de las sequences_of_statements, dependiendo del valor (de verdad) de una o mas condiciones correspondientes.

    ```ADA
    if_statement ::=
        if condition then
          sequence_of_statements
       {elsif condition then
          sequence_of_statements}
       [else
          sequence_of_statements]
        end if;
    ```

    Para la ejecución del if_statement, la condicion especificada luego del if, y cualquier otra condición especificada luego del elseif, son evaluadas sucesivamente(tratando el else final como si fuera un elseif en true), hasta que una de ellas sea verdadera o sean todas falsas. Si una condición resulta ser verdadera, entonces la correspondiente sequence_of_statements se ejecutanñ de otro modo ninguna de ellas se ejecuta.

+ C

    ```C
    	if (condición) {
    		sentencias_si_verdadero;
    	} else {
    		sentencias_si_falso;
    	}
    ```

    La condición, encerrada entre paréntesis, es una expresión que puede dar como resultado 0 (interpretado como falso) o cualquier valor distinto de 0 (interpretado como verdadero). Cuando la condición sea verdadera, se ejecutarán las sentencias dentro del primer bloque de código, cuando la condición sea falsa, se ejecutarán las sentencias del segundo bloque de código. Las expresiones y valores de tipo verdadero/falso son también llamados valores lógicos o booleanos.
    La indentación o sangría (los espacios al comienzo de las líneas) no es necesaria, pero ayuda a la claridad del código. La utilización de las llaves {...} es obligatoria cuando se quiere utilizar más de una instrucción por bloque, y optativa cuando sólo se quiere escribir una instrucción. Por claridad, sin embargo, es recomendable utilizarlas aún cuando sólo vaya a haber una instrucción.
    El bloque del else es opcional. Si no se lo encuentra, sólo se realizará la acción correspondiente al bloque if.

+ Python

    ```Python
    x = int(input("Please enter an integer: "))
    Please enter an integer: 42
    if x < 0:
        x = 0
        print('Negative changed to zero')
    elif x == 0:
        print('Zero')
    elif x == 1:
        print('Single')
    else:
        print('More')
    ```

    Pueden haber cero o mas partes de tipo elif, y el else es opcional. La palabra clave elif es la abreviatura de ‘else if’. La secuencia if … elif … elif … es un sustituto al switch o case encontrados en otros lenguajes.
    En Python, luego de los dos puntos(:), las líneas que formen parte del if deben estar indentadas.
