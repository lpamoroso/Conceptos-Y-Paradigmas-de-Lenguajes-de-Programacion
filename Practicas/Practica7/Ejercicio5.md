# Ejercicio 5

1. ¿Permite C tomar el l-valor de las variables? Ejemplificar.
2. ¿Qué problemas existen en el manejo de punteros? Ejemplificar.

#

1. Si, anteponiendo & a una variable cualquiera se puede saber su referencia. Por ejemplo, si yo tengo una variable x y le antepongo & (&x) puedo saber cual es su direccion de memoria.

2. Existen los problemas con respecto a liberar un puntero siendo que este tenga varias referencias. En este caso el puntero apunta a basura. Tambien podria darse un acceso descontrolado a posiciones de memoria inexistentes. En este caso conviene inicializar los punteros con un valor como podria ser nil o null, dependiendo el lenguaje.
