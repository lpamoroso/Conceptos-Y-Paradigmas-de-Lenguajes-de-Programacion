# Ejercicio 2

Unir los siguientes puntos según corresponda y de una definición y un ejemplo de cada par.

```
                                                                             Resultado
                                                                             Valor
Modo IN                                                                      Valor / Resultado
Modo OUT                                                                     Nombre
modo IN / OUT                                                                Resultado de funciones
                                                                             Valor Constante
                                                                             Referencia
```

* Modo IN  
  * Por Valor
    + El valor del parámetro real se usa para inicializar el correspondiente parámetro real al invocar la unidad. 
    + Se transfiere el dato real.
    + En este caso el parámetro formal actúa como una variable local de la unidad llamada.  
    * **Desventaja**
      + Consume el tiempo para hacer la copia y el almacenamiento para duplicar el dato.  
    * **Ventaja**
      + Protege los datos de la unidad llamadora, el parámetro real no se modifica.
  * Por valor constante
    + No indica si se realiza o no la copia, lo que establece es que la implementación debe verificarque el parámetro real no sea modificado.
    + Ejemplo: parámetros IN de ADA.  
  **Desventaja**: requiere realizar mas trabajo para implementar los controles.  
  **Ventaja**: protege los datos de la unidad llamadora, el parámetro real no se modifica.

* Modo OUT
  * Por Resultado
    + El valor del parámetro formal se copia al parámetro real al terminar de ejecutarse la unidad llamada.
    + El parámetro formal es una variable local, sin valor inicial.
    + **Desventajas**
      * Consume tiempo y espacio
      * Si se repiten los parámetros reales los resultados pueden ser diferentes.
      * Se debe tener en cuenta el momento en que se evalúa el parámetro real
    + **Ventaja**
      * Protege los datos de la unidad llamadora, el parámetro real no se modifica en la ejecución de la unidad llamada
  * Por resultado de funciones
    + El resultado de una función puede devolverse con el return como en Python, C, etc.,  o como en Pascal en el nombre de la función (ultimo valor asignado) que se considera como una variable local.
    + Dicho resultado reemplaza la invocación en la expresión que contiene el llamado.
    
* Modo IN/OUT
  + Por Valor/Resultado
    * Copia a la entrada y a la salida de la activación de la unidad llamadora.
    * El parámetro formal es una variable local que se recibe una copia a la entrada del contenido del parámetro real y a la salida el parámetro real recibe una copia de lo que tiene el parámetro formal.
    * Cada referencia al parámetro formal es una referencia local.
    * **Tiene las desventajas y las ventajas de ambos.**
  + Por Referencia
    * Se transfiere la dirección del parámetro real al parámetro formal. El parámetro formal será una variable local a la unidad llamadora que contiene la dirección en el ambiente no local.
    * Cada referencia al parámetro formal será a un ambiente no local. Esto significa que cualquier cambio que se  realice en el parámetro formal dentro del cuerpo del subprograma quedará registrado en el parámetro real.
    * El parámetro real es compartido por la unidad llamada.
    * **Desventajas**
      + El acceso al dato es mas lento por la indirección
      + Se pueden modificar el parámetro real inadvertidamente
      + Se pueden generar alias y estos afectan la legibilidad y por lo tanto la confiabilidad, hacen muy difícil la verificación de programas.
    * **Ventaja**
      + Eficiente en tiempo y espacio. No se realizan copias del dato
+ Por Nombre: 
  * El parámetro formal es sustituido textualmente por el parámetro real.
  * Es decir, se establece la ligadura entre parámetro formal y parámetro real en el momento de la invocación pero la ligadura de valor se difiere hasta el momento en que se lo utiliza.
  * El objetivo es otorgar mayor flexibilidad a través de esta evolución de valor diferida.
  * Si el dato a compartir es: 
    + Un único valor se comporta exactamente igual que el pasaje por referencia.
    + Si es una constante es equivalente a por valor.
    + Si es un elemento de un arreglo puede cambiar el suscripto entre las distintas referencias.
    + Si es una expresión se evalúa cada vez.
