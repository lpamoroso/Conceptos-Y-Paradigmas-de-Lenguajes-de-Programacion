# Ejercicio 4

Cuando se termina de manejar la excepción, la acción que se toma luego es importante. Indique:
1. ¿Qué modelos diferentes existen en este aspecto?
2. Dé ejemplos de lenguajes que utilizan cada uno de los modelos presentados anteriormente. Por
cada uno responda respecto de la forma en que trabaja las excepciones.
    1. ¿Cómo se define?
    2. ¿Cómo se lanza?
    3. ¿Cómo se maneja?
    4. ¿Cuál es su criterio de continuación?
3. ¿Cuál de esos modelos es más inseguro? ¿Por qué?

#

1. Existen dos tipos de modelo de manejo de excepciones:
+ *Reasunción*: se maneja la excepción y se devuelve el control al punto siguiente donde se invoco la
excepción, permitiendo la continuación de ejecución de la unidad.
+ *Terminación*: se termina la ejecución de la unidad que alcanza la excepción y se transfiere el control al manejador.

2.
+ Reasuncion: PL/1.
+ Terminacion: ADA, CLU.

## PL/1

Utiliza el criterio de Reasunción, es decir que se maneja la excepción y se devuelve el control al punto siguiente donde se invoco la excepción, permitiendo la continuación de ejecución de la unidad.
Las excepciones son llamadas CONDITIONS  y los manejadores se declaran con la sentencia ON y el manejador puede ser una instrucción simple o un bloque.

```PL/1
ON CONDITION (nombreExcepcion) manejadroDeExcepcion
```

Las excepciones se alcanzan explicitamente con la sentencia SIGNAL CONDITION (NombreExcepcionALanzar).
Este lenguaje provee de un conjunto de excepciones incorporadas (built_in exceptions) con sus propios manejadores y se alcanzan automáticamente en la ejecución de algunas sentencias. Por ejemplo, ZERODIVIDE se usa en la evaluación de una expresión para chequear que el denominador de una división se encuentra en cero.
La acción realizada por un manejador la especifica el lenguaje pero puede ser redefinida como una excepción del usuario.

```PL/1
ON ZERODIVIDE BEGIN;
...
END;
```

Éstas excepciones pueden ser habilitadas y deshabilitadas explícitamente. Se habilitan anteponiendo el nombre de la built_in antes del bloque, instrucción o procedimiento al que van a afectar. Se deshabilitan anteponiendo NO al nombre de la built_in antes del bloque, instrucción o procedimiento al que van a afectar. Por ejemplo:

```PL/1
(ZERODIVIDE):  BEGIN ... END
; //habilitada
(NOZERODIVIDE):  BEGIN ... END;
//deshabilitada.
```

Los manejadores se ligan dinámicamente con las excepciones con el último manejador definido. Si en el mismo bloque hay varias sentencias ON para la misma excepción, cada nuevo enlace anula al anterior. Si aparece una sentencia ON para la misma excepción en un bloque interno, el nuevo enlace permanece vigente solo hasta que acabe el bloque interno. Cuando salimos de un bloque, se restauran los enlaces que existían en la entrada del bloque anterior. El alcance de un manejador de una excepción termina cuando finaliza la ejecución de la unidad donde fue declarado. El alcance de un manejador de una excepción se acota cuando se define otro manejador para esa excepción y se restaura cuando se desactivan los manejadores que la enmascararon.
Podemos concluir que el enlace es dinámico entre una excepción y su manejador por lo tanto los programas en PL/1 pueden ser poco manejables, difíciles de comprender y escribir. Además no se permiten pasar parámetros desde el punto donde se produce la excepción al correspondiente manejador. Por consiguiente, solo se puede establecer el flujo de información mediante as variables globales. Por ejemplo, cuando se alcanza la excepción STRINGRANGE que indica un intento de acceder mas allá del limite de una cadena de caracteres, no hay manera de que el manejador sepa a qué cadena se refiere si hubiera dos o mas cadenas visibles en el ámbito. Tales situaciones hacen que el manejador de excepciones en PL/1 sea a menudo ineficaz.

## Ada

Utiliza el criterio de Terminación. Cada vez que se produce una excepción se termina el bloque, procedimiento, paquete o tarea donde se levanto y se ejecuta el manejador asociado.
Las excepciones se declaran en la zona de definición de variables, colocando la palabra Exception, e: exception. El alcance de una excepción es el mismo alcance de las variables. Las excepciones se alcanzan explícitamente con la palabra clave raise.

```Ada
RAISE (NombreExcepcionALanzar)
```

Los manejadores se encuentran en el final de cuatro diferentes unidades de programa: Bloque, Procedimiento, Paquete o Tarea. Forma de definirlos:

```ada
...
Begin
....
exception
when nomExcep1 => Manejador1
when  nomExcep2 => Manejador2
.....
when OTHERS  => Manejador (opcional);
End;
```

Ada ya tiene cuatro excepciones predefinidas con su manejador asociado. Estas pueden ser:
+ Constraint_Error: Falla un chequeo en tiempo de ejecución sobre alguna limitación (por ejemplo: fuera del limite en un arreglo).
+ Program_Error: Falla un chequeo en tiempo de ejecución sobre alguna regla del lenguaje.
+ Storage_Error: Falla un chequeo de tiempo de ejecución sobre la disponibilidad de memoria (por ejemplo por alocación dinámica).
+ Tasking_Error: Falla un chequeo de tiempo de ejecución en el sistema de task (por ejemplo en el manejo y la comunicación de tareas).
En algunas ocasiones, se necesita levantar de nuevo la excepción colocando solamente la palabra raise SIN NOMBRAR la excepción.
El pasaje de Parámetros únicamente se puede pasar como parámetro una cadena de caracteres.

## CLU

Utiliza el criterio de terminación.
Las excepciones sólo pueden ser alcanzadas por los procedimientos. Las excepciones que un procedimiento puede alcanzar han de declararse en la cabecera del mismo. Las excepciones se asocian a sentencias.
Las excepciones se alcanzan explicitamente con la palabra clave signal.

```CLU
SIGNAL (NombreExcepcionALanzar)
```

El manejador de excepciones se relaciona con las sentencias simples o complejas por medio de la cláusula except, según la sintaxis:

```CLU
<sentencia>
except
when
 nomExcep1: Manejador1
when
  nomExcep2: Manejador2
.....
when
OTHERS
  => Manejador (opcional);
     end
```

El lenguaje ya tiene excepciones predefinidas con su manejador asociado.
Al producirse una excepción:
+ Se termina el procedimiento donde se levanto la excepción y devuelve el control al llamante
inmediato donde se debe encontrar el manejador.
+ Si el manejador se encuentra en ese ámbito entonces se ejecuta y luego el control pasa a la sentencia siguiente a la que esta ligado dicho manejador.
+ Si el manejador no se encuentra en ese ámbito, la excepción se propaga estáticamente. Esto significa que el proceso se repite para las sentencias incluidas estáticamente.
+ En caso de no encontrar un manejador en el procedimiento que hizo la llamada, el procedimiento señala implícitamente a la excepción predefinida FAILURE y devuelve el control.
En CLU las excepciones pueden devolver parámetros a sus manejadores.
Las excepciones pueden ser vueltas a levantar con RESIGNAL.

3. El modelo por reasuncion es mas inseguro dado que cuando surge una excepcion no termina, sigue ejecutando donde se quedo y puede que eso acarree errores en la ejecución.
