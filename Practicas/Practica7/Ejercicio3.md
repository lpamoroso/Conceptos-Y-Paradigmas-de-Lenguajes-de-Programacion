# Ejercicio 3

1. Dar una breve definición de: producto cartesiano (en la bibliografía puede aparecer también como product type), correspondencia finita, uniones(en la bibliografía puede aparecer también como sum type) y tipos recursivos.
2. Identificar a qué clase de tipo de datos pertenecen los siguientes extractos de código. En algunos casos puede corresponder más de una:

<table>
  <tr>
    <td>
      <b>Java</b><br>
        Class Persona{<br>
        &nbsp;&nbsp;String nombre;<br>
        &nbsp;&nbsp;String apellido;<br>
        &nbsp;&nbsp;int edad;<br>
        }
    </td>
    <td>
      <b>C</b><br>
        typedef struct nodoLista{<br>
        &nbsp;&nbsp;void* dato;<br>
        &nbsp;&nbsp;struct nodoLista* siguiente<br>
        }nodoLista;<br>
        typedef struct lista{<br>
        &nbsp;&nbsp;int cantidad;<br>
        &nbsp;&nbsp;nodoLista* primero<br>
        }Lista;<br>
    </td>
    <td>
      <b>C</b><br>
        union codigo{<br>
        &nbsp;&nbsp;int numero;<br>
        &nbsp;&nbsp;char id;<br>
        };<br>
    </td>
  </tr>
  <tr>
    <td>
      <b>Ruby</b><br>
        hash = {<br>
        &nbsp;&nbsp;uno: 1,<br>
        &nbsp;&nbsp;dos: 2,<br>
        &nbsp;&nbsp;tres: 3,<br>
        &nbsp;&nbsp;cuatro: 4<br>
        }<br>
    </td>
    <td>
      <b>PHP</b><br>
        function doble($x){<br>
        &nbsp;&nbsp;return 2 * $x;<br>
        }<br>
    </td>
    <td>
      <b>Python</b><br>
        tuple = ('physics', 'chemistry', 1997, 2000)<br>
    </td>
  </tr>
  <tr>
    <td>
      <b>Haskell</b><br>
        data ArbolBinario Int =<br>
        &nbsp;&nbsp;Nil |<br>
        &nbsp;&nbsp;Nodo int<br>
        &nbsp;&nbsp;(ArbolBinarioInt dato)<br>
        &nbsp;&nbsp;(ArbolBinarioInt dato)<br>
      <b>Ayuda para interpretar:</b><br>
      ‘ArbolBinarioInt’ es un<br>
      tipo de dato que puede ser<br>
      Nil (“vacío”) o un Nodo con<br>
      un dato número entero (int)<br>
      junto a un árbol como hijo<br>
      izquierdo y otro árbol como<br>
      hijo derecho.<br>
    </td>
    <td>
      <b>Haskell</b><br>
        data Color =<br>
        &nbsp;&nbsp;Rojo |<br>
        &nbsp;&nbsp;Verde |<br>
        &nbsp;&nbsp;Azul<br>
        <b>Ayuda para interpretar:</b><br>
        ‘Color’ es un tipo de dato que<br>
        puede ser Rojo, Verde o Azul.<br>
    </td>
  </tr>
</table>

1. El producto cartesiano de dos conjuntos es una operación, que resulta en otro conjunto, cuyos elementos son todos los pares ordenados que pueden formarse de forma que el primer elemento del par ordenado pertenezca al primer conjunto y el segundo elemento pertenezca al segundo conjunto.
La unión / union discriminada de dos o mas tipos define un tipo como la disjunción de los tipos dados. Permite manipular diferentes tipos en distinto momento de la ejecución.
Un tipo de dato recursivo T se define como una estructura que puede contener componentes del tipo T. Define datos agrupados cuyo tamaño puede crecer arbitrariamente y cuya estructura puede ser arbitrariamente compleja.

2.
* Java
  + Class Persona: definido por el usuario compuesto tad.
  + String nombre;: predefinido compuesto.
  + String apellido;: predefinido compuesto.
  + int edad;: predefinido elemental.

* C
  + typedef struct nodoLista{: definido por el usuario producto cartesiano.
  + void* dato;: definido por el usuario recursivo.
  + struct nodoLista* siguiente: definido por el usuario.
  + typedef struct lista{: definido por el usuario producto cartesiano.
  + int cantidad;: predefinido elemental.
  + nodoLista* primero: definido por el usuario recursivo.

* C
  + union codigo{: definido por el usuario union.
  + int numero;: predefinido elemental.
  + char id;: predefinido elemental.

* Ruby
  + hash = {: definido por el usuario o predefinido.
  + uno: 1,: predefinido o definido por el usuario.
  + dos: 2,: predefinido o definido por el usuario.
  + tres: 3,: predefinido o definido por el usuario.
  + cuatro: 4: predefinido o definido por el usuario.

* PHP
  + function doble($x){: definido por el usuario tad.
  + $x:definido por el usuario o predefinido.

* Python
  + tuple = ('physics', 'chemistry', 1997, 2000): definido por el usuario.

* Haskell
  + data ArbolBinario Int =
  Nil |
  Nodo int
  (ArbolBinarioInt dato)
  (ArbolBinarioInt dato): definido por el usuario recursivo.

* Haskell
  + Haskell
    data Color =
      Rojo |
      Verde |
      Azul : definido por el usuario.
