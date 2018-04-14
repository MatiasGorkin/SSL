# 01 Fases de la Traduccion y Errores

2. comando: gcc hello2.c -e -p -o hello2.I

respuesta: archivo hello2.I generado

----------------------------------------------------------------------------------------------------------------------------------------

4. en la primera linea se desarrolla un prototipo de la funcion printf

----------------------------------------------------------------------------------------------------------------------------------------

5. no se encuentran diferencias entre hello3.c y hello3.I

----------------------------------------------------------------------------------------------------------------------------------------

6. comando: gcc hello3.I -S

respuesta:

hello3.I: In function 'main':

hello3.I:4:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]

  prontf("La respuesta es %d\n");

  ^~~~~~

hello3.I:4:2: error: expected declaration or statement at end of input

----------------------------------------------------------------------------------------------------------------------------------------

10. comando: gcc hello4.o -o hello4.exe

respuesta: 

hello4.o:hello4.I:(.text+0x1e): undefined reference to `prontf'

collect2.exe: error: ld returned 1 exit status

----------------------------------------------------------------------------------------------------------------------------------------

12. comando: hello5.exe

respuesta:

La respuesta es 4200768

----------------------------------------------------------------------------------------------------------------------------------------

14. comando: hello7.exe

respuesta:

hello7.c: In function 'main':

hello7.c:3:2: warning: implicit declaration of function 'printf' [-Wimplicit-function-declaration]

  printf("La respuesta es %d\n", i);

  ^~~~~~

hello7.c:3:2: warning: incompatible implicit declaration of built-in function 'printf'

hello7.c:3:2: note: include '<stdio.h>' or provide a declaration of 'printf'

----------------------------------------------------------------------------------------------------------------------------------------

15. El programa funciona debido al procedimiento de declaracion implicita que contiene,
por lo que puede deducir el comportamiento de la funcion. (Aunque en el sistema lo considere como 
warning ya que es incorrecto)
