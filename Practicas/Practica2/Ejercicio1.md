Ejercicio 1
======
Complete el siguiente cuadro:

<TABLE>
	<TR>
		<TH COLSPAN=2>Meta-símbolos utilizados por</TH>
		<TH>Símbolo utilizado en diagramas sintácticos</TH>
    <TH>Significado</TH>
	</TR>
	<TR>
		<TH>BNF</TH> <TH>EBNF</TH>
		<TH colspan=2></TH>
	</TR>
	<TR>
		<TD>Palabra terminal</TD> <TD>Palabra terminal</TD> <TD>Óvalo</TD> <TD>Definición de un elemento terminal.</TD>
	</TR>  
	<TR>
		<TD>dígito</TD> <TD>dígito</TD> <TD>Rectángulo</TD> <TD>Definición de un elemento no terminal.</TD>
	</TR>
	<TR>
		<TD>::=</TD> <TD>::=</TD> <TD>Diagrama con rectángulos, óvalos y flechas</TD> <TD>Meta-símbolo de definición que indica que el elemento a su izquierda se puede definir segin el esquema de la derecha.</TD>
	</TR>
	<TR>
		<TD>|</TD> <TD>(|)</TD> <TD>Flecha que se divide en dos o más caminos</TD> <TD>Meta-símbolo de opción que indica que puede elegirse uno y solo uno de los meta-símbolos.</TD>
	</TR>
	<TR>
		<TD>< p > < p1 ></TD> <TD>{}</TD> <TD></TD> <TD>Repetición.</TD>
	</TR>
	<TR>
		<TD>------------------</TD> <TD>*</TD> <TD></TD> <TD>Repetición de 0 o más veces.</TD>
	</TR>
	<TR>
		<TD>------------------</TD> <TD>+</TD> <TD></TD> <TD>Repetición de 1 o más veces.</TD>
	</TR>
	<TR>
		<TD>------------------</TD> <TD>[]</TD> <TD></TD> <TD>Elemento optativo(puede o no estar).</TD>
	</TR>
</TABLE>

**Nota**: *p y p1 son producciones simbólicas.*
