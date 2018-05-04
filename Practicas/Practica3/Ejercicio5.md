Ejercicio 5
======
Sean los siguientes ejemplos de programas. Analice y diga qué tipo de error se produce (Semántico o Sintáctico)y en qué momento se detectan dichos errores (Compilación o Ejecución).
Aclaración: Los valores de la ayuda pueden ser mayores.

1. Pascal
```pascal
Program P
  var 5: integer;
  var a:char;
Begin
  for i:=5 to 10 do begin
    write(a);
    a=a+1;
  end;
End.
```
*Ayuda: Sintáctico 2, Semántico 3*

|Error| Tipo |
|:---:|:---------:|
|var 5: integer;|Es **sintáctico** ya que una variable (en pascal) no puede empezar con números. El error lo detecta el compilador.|
|for i:=5 to 10 do begin|Esta sentencia tiene dos errores **semánticos**. El primero esta dado si y solo si consideramos que la variable 5 existiera. La cuestión pasaría por no haber inicializado la variable 5 y que el valor fuera basura. Es un error que sería detectado durante la ejecución. El segundo pasa porque la variable i no esta declarada. El error tambien lo detecta el compilador.|
|write(a);|Es un error **semántico** ya que, si bien a esta declarada, no está inicializada e imprimirá basura. El error se pude apreciar durante la ejecución.|
|a=a+1;|Esta sentencia tiene dos errores **sintácticos**. El primero se da ya que la variable a es un char y no se puede aplicarle la operación suma a tales variables. El error lo tira el compilador. El segundo se relaciona con que, en pascal, la asignacion es := en lugar de =. El error tambien lo arroja el compilador.|

2. Java:
```java
public String tabla(int numero, arrayList<Boolean> listado)
{
  String result = null;
  for(i = 1; i < 11; i--) {
    result += numero + "x" + i + "=" + (i*numero) + "\n";
    listado.get(listado.size()-1)=(BOOLEAN)numero>i;
  }
  return true;
}
```
*Ayuda: Sintácticos 4, Semánticos 3, Lógico 1*

|Error| Tipo |
|:---:|:---------:|
|public String tabla(int numero, arrayList<Boolean> listado)|En este caso el error es **sintáctico** ya que la clase arrayList no existe(no así la clase ArrayList). El error se detecta en compilación.|
|String result = null;|En este caso habría un error **semántico** si y solo si se quisiera dar a la variable el valor de null(vacío). El error se detecta durante la ejecución.|
|for(i = 1; i < 11; i--) {|Tiene un error **lógico** ya que el bucle no tendria fin. Se detecta durante la ejecución. Ademas, la sentencia tiene un error **semántico**: la variable i no esta declarada.|
|listado.get(listado.size()-1)=(BOOLEAN)numero>i;|Esta linea tiene muchos problemas. En concreto, tiene 2 **sintácticos** y 1 **semántico**. Voy a suponer que la sentencia intenta ser de asignación. Si así fuera, a la izquierda requiere una variable. Ese seria el primer error **sintáctico**. La sentencia a la izquierda no tiene razón para ser analizada(la única forma en que tendría sentido analizarla sería en que en vez de que la sentencia fuera de asignación, que fuera de condición, pero ya antes establecí que la sentencia la supondría de asignación); sin embargo, la analicé y es sintácticamente correcta (si la clase fuera ArrayList en lugar de arrayList). La sentencia a la derecha, sin embargo, sí tiene un error, esta vez semántico. Si bien en java se puede castear de un tipo de variable a otro, no se puede de Integer a Boolean. Ese es el error **semántico**. Por otro lado, un error **sintáctico** es que la clase se llama Boolean y no BOOLEAN. Todos los errores se detectan durante la compilación.|
|return true;|Es un error **semántico** ya que la función debería retornar un String en lugar de un Boolean.|

3. C
```c
# include <stdio.h>
int suma; /* Esta es una variable global */
int main()
{ int indice;
  encabezado;
  for (indice = 1 ; indice <= 7 ; indice ++)
  cuadrado (indice);
  final(); Llama a la función final */
  return 0;
}
cuadrado (numero)
int numero;
{ int numero_cuadrado;
  numero_cuadrado == numero * numero;
  suma += numero_cuadrado;
  printf("El cuadrado de %d es %d\n",
  numero, numero_cuadrado);
}
```
*Ayuda: Sintácticos 2, Semánticos 6*

|Error| Tipo |
|:---:|:---------:|
|encabezado;|En esta sentencia hay dos errores(suponiendo que lo que se quiera es llamar a una función): uno **semántico** y otro **sintáctico**. El error **semántico** es que la función encabezado no está declarada. El error **sintáctico** es que está mal definido el llamado a la función: el nombre de la función  y el ; está, pero faltan los () entre medio.|
|cuadrado (indice);|El error es de tipo **semántico**: la función cuadrado no está declarada.|
|final(); Llama a la función final */|En esta línea hay dos errores **semánticos**. El primero es que se está cerrando un comentario que nunca se abrio. El segundo es que la función final no está declrada.|
|cuadrado (numero)|En esta sentencia hay dos errores: dos **semánticos** y uno **sintáctico**. Un error **semántico** es que la función cuadrado no está declarada. El otro error **semántico** es que la variable número no esta declarada. El error **sintáctico** es que falta el ; al final de la sentencia.|
|{ int numero_cuadrado;|Es un error **sintáctico** ya que está mal definida la declaración de la función.|
|numero_cuadrado == numero * numero;|El error es **semántico** porque si bien la sentencia es válida, número no esta inicializada.|
|suma += numero_cuadrado;|Dos errores **semánticos**: tanto suma como numero_cuadrado no están inicializados.|
|printf("El cuadrado de %d es %d\n", numero, numero_cuadrado);|Son dos errores semánticos solo en el caso de que las dos variables que se imprimen no estuvieran inicializadas.|

4. Python
```python
#!/usr/bin/python
print "\nDEFINICION DE NUMEROS PRIMOS"
r = 1
while r = True:
  N = input("\nDame el numero a analizar: ")
  i = 3
  fact = 0
  if (N mod 2 == 0) and (N != 2):
    print "\nEl numero %d NO es primo\n" % N
  else:
    while i <= (N^0.5):
      if (N % i) == 0:
        mensaje="\nEl numero ingresado NO es primo\n" % N
        msg = mensaje[4:6]
        print msg
        fact = 1
      i+=2
    if fact == 0:
      print "\nEl numero %d SI es primo\n" % N
  r = input("Consultar otro numero? SI (1) o NO (0)--->> ")
```
*Ayuda: Sintácticos 2, Semánticos 3*

|Error| Tipo |
|:---:|:---------:|
|while r = True:|Es un error **semántico** ya que la comparación del while es entre un entero y un Boolean y eso no se puede hacer pero la sentencia es sintácticamnte válida.|
|if (N mod 2 == 0) and (N != 2):|Es un error **sintáctico** ya que la operación mod no existe.|
|while i <= (N^0.5):|Es un error **sintáctico** ya que la operación ^ no existe.|
|mensaje="\nEl numero ingresado NO es primo\n" % N|Es un error **semántico** ya que omite uno de los argumentos pero la sentencia es sintácticamente válida.|
|msg = mensaje[4:6]|El error es **semántico** porque corta mal el string.|

5. Ruby
```ruby
def ej1
  Puts 'Hola, ¿Cuál es tu nombre?'
  nom = gets.chomp
  puts 'Mi nombre es ', + nom
  puts 'Mi sobrenombre es 'Juan''
  puts 'Tengo 10 años'
  meses = edad*12
  dias = 'meses' *30
  hs= 'dias * 24'
  puts 'Eso es: meses + ' meses o ' + dias + ' días o ' + hs + ' horas'
  puts 'vos cuántos años tenés'
  edad2 = gets.chomp
  edad = edad + edad2.to_i
  puts 'entre ambos tenemos ' + edad + ' años'
  puts '¿Sabes que hay ' + name.length.to_s + ' caracteres en tu nombre, ' + name + '?'
end
```
|Error| Tipo |
|:---:|:---------:|
|Puts 'Hola, ¿Cuál es tu nombre?'|El error es **sintáctico**: error de tipeo en Puts(en realidad va puts)|
|puts 'Mi sobrenombre es 'Juan''|El error es **semántico**: se supone que se intenta escribir "Mi sobrenombre es 'Juan'". Esa no es la forma de hacerlo.|
|meses = edad * 2|El error es **semántico**: la variable edad no esta declarada.|
|dias = 'meses' * 30|Podría haber un error **semántico** si lo que se pretende es hacer una multiplicación por 30 de la variable meses en lugar de escribir 30 veces meses.|
|hs= 'dias * 24'|Idem caso anterior: podría haber un error **semántico** si lo que se pretende es hacer una multiplicación por 24 de la variable dias en lugar de escribir dias * 24 como string.|
|puts 'Eso es: meses + ' meses o ' + dias + ' días o ' + hs + ' horas'|El error es **sintáctico**: hay fallos a la hora de concatenar, variables que no existen|
|puts 'entre ambos tenemos ' + edad + ' años'|El error es **sintáctico**: se esta intentando concatenar de manera incorrecta|


*Ayuda: Semánticos +4*
