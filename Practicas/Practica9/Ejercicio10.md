# Ejercicio 10

Determine si el lenguaje que utiliza frecuentemente implementa instrucciones para
el manejo de espacio de nombres. Mencione brevemente qué significa este concepto y enuncie
la forma en que su lenguaje lo implementa. Enuncie las características más importantes de este
concepto en lenguajes como PHP o Python.

Un namespace esta diseñado para sobreponerse a esta dificultad y es usado como informacion adicional para diferenciar funciones similares, clases, variables, etc. con el mismo nombre disponible en diferentes bibliotecas. Usando namespace se puede difinir el contexto en el cual los nombres son definidos. En esencia, un namespace define un alcance. En c++, por ejemplo un namespace es definido de la siguiente manera.

```c++
#include <iostream>
using namespace std;

// first name space
namespace first_space {
   void func() {
      cout << "Inside first_space" << endl;
   }
}

// second name space
namespace second_space {
   void func() {
      cout << "Inside second_space" << endl;
   }
}

int main () {
   // Calls function from first name space.
   first_space::func();

   // Calls function from second name space.
   second_space::func();

   return 0;
}
```

Como puede apreciarse, en este caso, el namespace tiene dos usos:
+ El primero, en *using namespace std;*. Esta directiva le dice al compilador que el codigo subsecuente esta haciendo uso de nombres en el namespace especificado. Tambien puede indicarse la funcion de la que se quiere hacer uso.
+ El segundo, como informacion adicional para determinar a que funcion se hace referencia.

En python, hay diferentes tipos de namespaces y lo interesante es que cada uno de ellos es un diccionario, por lo que un namespace representa una coleccion de nombres. Se clasifican en:

+ Namespace local: este namespace incluye nombres locales dentro de una funcion y es creado cuando una funcion es llamada y dura hasta que la funcion llama al return.
+ Namespace global: este namespace incluye nombre de varios modulos importados que se estan usando en el proyecto. Es creado cuando el modulo es incluido en el proyecto y dura hasta que el script termine.
+ Namespaces integrados: Este namespace incluye funciones integradas y nombres de excepciones integrados.

En PHP, los namespaces son una manera de encapsular elementos. Se pueden ver como un concepto abstracto en muchos aspectos. Por ejemplo, en cualquier sistema operativo, los directorios sirven para agrupar ficheros relacionados, actuando así como namespaces para los ficheros que contienen. Como ejemplo, el fichero foo.txt puede existir en los directorios /home/greg y /home/otro, pero no pueden coexistir dos copias de foo.txt en el mismo directorio. Además, para acceder al fichero foo.txt fuera del directorio /home/greg, se debe anteponer el nombre del directorio al nombre del fichero, empleando el separador de directorios para así obtener /home/greg/foo.txt. Este mismo principio se extiende a los namespaces en el mundo de la programación.
En el mundo de PHP, los espacios de nombres están diseñados para solucionar dos problemas con los que se encuentran los autores de bibliotecas y de aplicaciones al crear elementos de código reusable, tales como clases o funciones:

1. El conflicto de nombres entre el código que se crea y las clases/funciones/constantes internas de PHP o las clases/funciones/constantes de terceros.
2. La capacidad de apodar(o abreviar) Nombres_Extra_Largos diseñada para aliviar el primer problema, mejorando la legibilidad del código fuente.

Los espacios de nombres de PHP proporcionan una manera para agrupar clases, interfaces, funciones y constantes relacionadas. Un ejemplo de la sintaxis de los espacios de nombres de PHP:
```PHP
<?php
    namespace mi\nombre; // véase la sección "Definir espacios de nombres"

    class MiClase {}
    function mifunción() {}
    const MICONSTANTE = 1;

    $a = new MiClase;
    $c = new \mi\nombre\MiClase; // véase la sección "Espacio global"

    $a = strlen('hola'); // véase la sección "Utilizar espacios de nombres: una
                         // alternativa a funciones/constantes globales"

    $d = namespace\MICONSTANTE; // véase la sección "El operador namespace y
                                // la constante __NAMESPACE__"
    $d = __NAMESPACE__ . '\MICONSTANTE';
    echo constant($d); // véase la sección "Espacios de nombres y características dinámicas del lenguaje"
?>
```
