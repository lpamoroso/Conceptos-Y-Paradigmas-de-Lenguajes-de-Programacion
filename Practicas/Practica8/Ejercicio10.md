# Ejercicio 10

¿Qué modelo de excepciones implementa Ruby? ¿Qué instrucciones específicas provee el lenguaje para manejo de excepciones? ¿Cómo se comportan cada una de ellas?  

Una excepción es un tipo especial de objeto de la clase Exception. Para tratar el problema hace falta raise; de no ser así, el programa termina y avisa del error. Lo que hará raise (lanzar), será lanzar una "excepción" para manejar el error.  
Ruby tiene una serie de clases, Exception y sus hijas, que ayudan a manejar los errores que pueden ocurrir. La siguiente figura enseña la jerarquía en Ruby:

```ruby
def lanzar_excepcion
  puts 'Estoy antes del raise'
  raise 'Se ha producido un error' # lanza una excepción con el mensaje entre ''
  puts 'Estoy despues del raise'
end

lanzar_excepcion
```
