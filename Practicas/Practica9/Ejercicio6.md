# Ejercicio 6

¿Cuál es la construcción para expresar múltiples selección que implementa C? ¿Trabaja de la misma manera que la de Pascal, ADA o Python?

+ C

    La sentencia switch y case ayudan a controlar operaciones condicionales y de derivación complejas. La sentencia switch transfiere el control a una de las sentencias dentro de su cuerpo.

    El control pasa a aquella sentencia en la que la expresion constante iguale al valor de la variable del switch. La sentencia switch puede incluir cualquier numero de sentencias case, pero no dos constantes case dentro del mismo switch que contengan el mismo valor. La ejecución de las instrucciones del cuerpo de un case comienza cuando éste es seleccionado y no se detiene encontrar una sentencia break o el fin de la sentencia switch.

    ```C
    switch ( expression )
    {
        case constant-expression :
            statements executed if the expression equals the
            value of this constant-expression
        break;
        default :
            statements executed if expression does not equal
            any case constant-expression
    }
    ```

    Puede usar la sentencia break para concluir el procesamiento de un case en particular dentro de la sentencia switch y para derivar al fin de una sentencia switch. Sin un break, el programa continua hacia el siguiente caso, ejecutando las instrucciones hasta encontrar el fin del switch o un break. En algunas situaciones, dicho comportamiento puede ser deseable; en la mayoria de las situaciones, no es así.

+ Ada

    Por lo general es necesario comparar ona variable especifica contra varias expresiones constantes. Para este tipo de expresiones condicionales existe la sentencia case.

    ```Ada
    case X is
       when 1 =>
          Walk_The_Dog;
       when 5 =>
          Launch_Nuke;
       when 8 | 10 =>
          Sell_All_Stock;
       when others =>
          Self_Destruct;
    end case;
    ```

    El subtipo de X debe ser un tipo discreto, por ejemplo un enumerativo o un entero.

    En Ada, una de las ventajas de la sentencia case es que el compilador evalúa la cobertura de la elecciones, esto es, todos los valores del subtipo de la varible X deben estar presentes o un derivador por defecto when others debe especificar qué hacer en los casos restantes.

+ Pascal

    Las constantes que aparecen en los diferentes casos deben ser conocidos en el momento de la compilacion, y pueden ser de los siguientes tipos: tipo enumerativo, tipo ordinal(incluyendo chars) o tipo string. La expresion del case debe ser, ademas, de ese tipo o ocurrira un error en la compilacion. Todas las constantes del case deben tener el mismo tipo.
    El compilador evaluara la expresion del case. Si uno de los valores de las constantes de los case iguala el valor de la expresion, la sentencia que sigue a esa constante es ejecutada. Luego de eso, el programa continua desde el del ultimo end.
    Si ninguna de las constantes del case iguala el valor de la expresion, la lista de sentencias luego de la palabra clave else u otherwise es ejecutada. Esta podria ser una lista de sentencias vacia. Si no hubiera un else, y ninguna constante de algun case igualara el valor de la expresion, el flujo del programa continua desde el ultimo end.
    La sentencia case pueden ser sentencias compuestas(bloques Begin..End, por ejemplo).


+ Python

    En Python no existe el switch-case, pero puede simularse usando diccionarios y excepciones.
