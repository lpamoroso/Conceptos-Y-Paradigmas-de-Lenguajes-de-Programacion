# Intro excepciones

1. ¿Qué es la recursión?

Un tipo de dato recursivo se define como una estructura que puede contener componentes del mismo tipo. La recursión es un mecanismo de estructuración para definir datos agrupados cuyo tamaño puede crecer arbitrariamente y cuya estructura puede ser arbitrariamente compleja.  
Para implementarla, los lenguajes de programación convencionales utilizan el concepto de los punteros, sin embargo, los lenguajes funcionales proveen mecanismos más abstractos que enmascaran a los punteros.

2. ¿Qué es un puntero?

Son estructuras de tamaño arbitrario sin un número de items determinado(datos anónimos). Características:
* Relaciones múltiples entre los items: varias estructuras sin necesidad de duplicarlo.
* Acceso a bajo nivel: los punteros están cerca de la máquina en su implementación.

Sin embargo, los punteros son estructuras inseguras por varias razones, entre ellas, una de sus características principales: el hecho de poder acceder a bajo nivel. La cierto es que pueden obscurecer o hacer inseguros a los programas que los usan.  
Algunas inseguridades:
* Violación de tipos
* Referencias sueltas - referencias dangling
* Liberación de memoria: objetos
* Liberación de memoria: objetos perdidos
* Punteros no inicializados
* Punteros y uniones discriminadas
* Alias

3. Liberación de memoria: objetos perdidos

Las variables puntero se alocan como cualquier otra variable en la pila de registros de activación. Los objetos apuntados que se alocan a través de la primitiva new son alocados en la heap. La memoria disponible(heap) podría rápidamente agotarse a menos que de alguna forma se devuelva el almacenamiento alocado liberado.
Hay varias situaciones en las que podría liberarse la memoria sin afectar el programa, por ejemplo, si los objetos en la heap dejan de ser accesibles.
Es en este contexto que es necesaria alguna forma de liberar la memoria, acá es donde aparece el garbage collector.
