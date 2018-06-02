# Ejercicio 12

Sea el siguiente código escrito en CLU

```CLU
Procedure Main
  Error1 : exception;
  x, y: integer;
  Procedure UNO () signals error1;
    x:integer
    Begin
    x:=2;
    ......
    While y < x Do
      If y=0 Then
        signal error1;
      end if;
      exception
        when error1 ->
          y:=y+7;
          x:=x+2;
          resignal;
      end;
      Dos();
      y:=y+1;
    Wend;
    exception
      when error1 ->
        y:=x+3;
        x:=x+3;
        resignal;
    End;
  End; //UNO
  Procedure Dos() signals error1;
    m:integer;
    Begin
    ...
    if m=0 then signal error1;
  End;
Begin //MAIN
  x:=1; y:=0;
  Uno(); exception when error1 ->
    x:=x+1;
    y:=y+1;
  end;
  ...
  Dos(): exception when error1 -> resignal;
  end;
  ...
End; //MAIN
```
1. Indique cómo se ejecuta el código. Debe quedar en claro los caminos posibles de ejecución, cuáles son los manejadores que se ejecutan y cómo se buscan los mismos y si en algún caso se produce algún error.
2. La ejecución del manejador para error1 modifica siempre la variable x de UNO? En caso negativo indique cómo haría para lograrlo. Justifique la respuesta.

#

1. Primero va a ejecutarse UNO(). Despues entra en el while y salta la excepcion. Termina uno y se sigue en la proxima linea a la llamada de uno, la cual es ...... Si en esa linea surge un problema, el programa termina ya que es la subrutina mas externa y no hay nadie que la llamo. Si no hay errores, luego se ejecuta Dos(). En dos, si se produce una excepcion de tipo error1, es manejada por el proceso main, pero el resignal no se puede llevar a cabo y termina ya que no hay nadie que llamo al main. Si no surgen excepciones durante los ...., si m es 0 se levanta una excepcion de tipo error1 y es manejada por el main, pero el resignal no se puede llevar a cabo y termina ya que no hay nadie que llamo al main. Si no, termina dos y termina el programa.

2. No, modifica siempre la del main. Para lograrlo la idea es pasar la variable a traves del signal y modificar esa variable recibida, de esa manera se modificaría la variable de UNO.
