# 01 Fases de la Traduccion y Errores

MatiasGorkin

1601295

Gorkin

Matias


**2**. comando: gcc hello2.c -e -p -o hello2.I

respuesta: archivo hello2.I generado

----------------------------------------------------------------------------------------------------------------------------------------

**4**. En la primera linea se desarrolla un prototipo de la funcion printf

----------------------------------------------------------------------------------------------------------------------------------------

**5**. comando: gcc hello3.c -e -p -o hello3.I 

No se encuentran diferencias entre hello3.c y hello3.I ya que no habia librerias incluidas para que el preprocesador incluya, ni comentarios para que reemplace por espacios.

----------------------------------------------------------------------------------------------------------------------------------------

**6**. comando: gcc hello3.I -S

respuesta:

**hello3.I: In function 'main':**

**hello3.I:4:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]**

**prontf("La respuesta es %d\n");**

**hello3.I:4:2: error: expected declaration or statement at end of input**

Se ve este error ya que el programa no finaliza con un corchete. Y tambien advierte sobre la declaracion implicita de prontf.

----------------------------------------------------------------------------------------------------------------------------------------

**7**. comando: gcc hello4.c -e -p -o hello4.I

            gcc hello4.I -S
            
resultado: Se generan archivos hello4.I y hello4.S

----------------------------------------------------------------------------------------------------------------------------------------

**9**. comando: gcc hello4.s -c

resultado: Se genera hello4.o

----------------------------------------------------------------------------------------------------------------------------------------

**10**. comando: gcc hello4.o -o hello4.exe

respuesta: 

**hello4.o:hello4.I:(.text+0x1e): undefined reference to `prontf'**

**collect2.exe: error: ld returned 1 exit status**

Se ve dicho error ya que no encuentra la funcion prontf definida en la libreria standard a la hora de linkear.

----------------------------------------------------------------------------------------------------------------------------------------

**11**. comando: gcc hello5.c -o hello5.exe

resultado: Se genera hello5.exe

----------------------------------------------------------------------------------------------------------------------------------------

**12**. comando: hello5.exe

respuesta:

La respuesta es 4200768

Muestra dicho numero ya que el sistema busco un valor, y ese valor considerandolo desde nuestro punto de vista es basura.

----------------------------------------------------------------------------------------------------------------------------------------

**13**. comando: gcc hello6.c -o hello6.exe

resultado: Se genera el archivo hello6.exe y funciona el programa como se esperaba.

----------------------------------------------------------------------------------------------------------------------------------------

**14**. comando: hello7.exe

respuesta:

**hello7.c: In function 'main':**

**hello7.c:3:2: warning: implicit declaration of function 'printf' [-Wimplicit-function-declaration]**

**printf("La respuesta es %d\n", i);**

**hello7.c:3:2: warning: incompatible implicit declaration of built-in function 'printf'**

**hello7.c:3:2: note: include '<stdio.h>' or provide a declaration of 'printf'**

Tira un aviso ya que esta utilizando la declaracion implicita ya que no se incluyo ninguna biblioteca ni se establecio un prototipo de la funcion printf.

----------------------------------------------------------------------------------------------------------------------------------------

**15**. El programa funciona debido al procedimiento de declaracion implicita que contiene,
por lo que puede deducir el comportamiento de la funcion. (Aunque en el sistema lo considere como 
warning ya que es un uso declarado como incorrecto)
