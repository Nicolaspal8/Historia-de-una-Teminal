# Guia de comandos en la terminal

1. **pwd** : Nos permite saber en que directorio estamos (point working directory)
2. **ls** : Nos permite Listar el contenido dentro del directorio donde estamos
3. **ls -l** : Muestra los archivos mas estructurados en forma de lista y especificando si es directorio o otro tipo de elemento, tambien especifica el peso de un archivo
4. **ls -lh** : Aun mas especifico y nos muestra el tamaño excacto de nuestros archivos
5. **clear (cls en windows) o ctrl+l**: limpia la consola
6. **cd** : (change directory) permite cambiar de directorio en el que nos encontramos es decir sirve para navegar entre directorios
7. **cd D + Tab*2** : cd seguido de la inicial de algun archivo que estamos buscando y presionando tab 2 veces nos muestra las coincidencias con dicha letra en el inicio de cada archivo
8. **cd ..** : Nos devuelve a donde estabamos anteriormente
9. **cd /desktop/archivo/Otro** : Permite acceder mas rapido si conocemos el trayecto a la ubicacion del archivo objetivo y es sensible a mayusculas
10. **cd** : te lleva al inicio de donde estabas a diferencia de cd .. retrocede mas de una carpeta o directorio
11. **cd /** : hace referencia a comenzar desde la raiz de directorios y en base a ese punto seguir navegando sobre los siguientes directorios
12. **./archivo.extension** : Abre un archivo ejecutable y mientras el programa este en ejecucion la terminal quedara ejecutandose junto con el programa es decir que deberiamos abrir otra terminal para seguir ejecutando otros comandos
13. **man [nombre de comando]** : Es el manual de un comando en especifico abre un lector en el bash de linux y para bajar hay que presionar 
+ enter = linea por linea
+ b = para devolverse
+ space = cambia de pagina
+ q = sale del lector
14. **cd ~** : hace referencia al home como cd solo el home es el usuario donde estamos logeados
15. **mkdir [nombre carpeta]** : Crea una carpeta
+ Puedo crear mas de una carpeta si separo cada nombre por un simple espacio
16. **mkdir [ruta donde quiero crear la carpeta]/[nombre de carpeta]** : Crea una carpeta en un directorio especifico sin necesidad de posicionarte en el
17. **mv [archivo a mover]/[destino archivo]** : (move)
18. **ls [nombre de carpeta que quiero saber el contenido]** : Muestra el contenido de una carpeta sin necesidad de estar en dicha carpeta sino que solo en el padre de donde esta esa carpeta
19. **ls ..** : Nos muestra lo que esta en la carpeta anterior a la que estamos es decir los hermanos de la carpeta ne la que estamos
20. **touch [nombre archivo.extension]** : Crea un archivo nuevo, no un directorio si no que un archivo con una extension
21. **touch [nombre de donde lo quiero crear]/[nombre archivo.extension]** : Crea un archivo en otra carpeta sin nececidad de estar en dicha carpeta si no que estando en el padre de la carpeta basta
22. **rm [nomobre de "archivo" a eliminar]** : Elimina un archivo sin confirmacion ni nada lo elimina directamente
23. **rm -rf [nombre de directorio a eliminar]** : Elimina un directorio o carpeta a eliminar
24. **cat [nombre de archivo](type en windows)** : Nos muestra el contenido dentro del archivo
25. **wich (where en windows) [nombre comando]** : Nos dice la ubicacion de un comando
26. **nano [archivo donde incertaremos contenido]** : Incerta contenido en un archivo a través de una interfas de usaurio
27. **mv [nombre archivo] [nuevo nombre archivo]** : Cambia el nombre de un archivo manteniendo el contenido de el
28. **top** : (Como tasklist en windows pero sin el control de comandos al apretar k) Nos muestra una lista de procesos que estan siendo ejecutados en nuestro computador
+ Ejemplo de Comandos en windows
~~~
1. taskkill /IM NombreDeimagen.exe /F
2. taskkill /PID xxxx /F (donde xxxx es el PID)
A continuación, veamos el significado de las opciones de Taskkill:
1. /F ? Fuerza el cierre de un proceso.
2. /IM ? Nombre de la imagen.
3. /PID ? Nombre del Proceso.
• Tskill como alternativa
En algunas computadoras, no existe taskkill.exe. Este ha sido reemplazado por
tskill.exe. Su funcionamiento es similar:
1. tskill Nombre_de_imagen.exe
2. tskill PID_del_proceso
Las opciones del comando son:
1. /A ? para terminar el proceso en todas las sesiones.
2. /V ? para terminar el proceso únicamente en la sesión.
3. /? ? Ayuda.
~~~
29. **Atajos de teclado**:
En el intérprete de la terminal Bash podemos usar las siguientes combinaciones de teclas:
+ **Ctrl+a** : lleva el cursor al inicio de la línea de comandos.
+ **Ctrl+e** : lleva el cursor al final de la línea de comandos.
+ **Ctrl+1** : limpia la terminal, similar a lo que hace el comando clear.
+ **Ctrl+u** : limpia desde la posición del cursor hasta el inicio de la línea. Si se está al final limpia la línea entera.
+ **Ctrl+k** : limpia desde la posición del cursor hasta el final de la línea. Si se está al inicio limpia la línea entera.
+ **Ctrl+h** : hace lo mismo que la tecla backspace, borra el caracter inmediatamente anterior a la posición del cursor.
+ **Ctrl+w** : borra la palabra inmediatamente antes del cursor.
+ **Alt+d o Esc+d** : borra la palabra siguiente después del cursor.
+ **Ctrl+p** : establece la línea de comandos con el último comando introducido.
+ **Ctrl+r** : inicia la búsqueda de comandos usados anteriormente, tecleando parte de un comando usos anteriores que hayamos realizado incluyendo las opciones y parámetros. Hecha una búsqueda pulsando de nuevo la combinación de teclas encontraremos coincidencias anteriores.
+ **Ctrl+c** : termina el proceso que se esté ejecutando, útil para recuperar el control del sistema.
+ **Ctrl+d** : sale de la terminal, similar al comando exit.
+ **Ctrl+z** : suspende la ejecución del proceso que se está ejecutando y lo pone en segundo plano, con el comando fg
podremos volver a continuar su ejecución.
+ **Ctrl+t** : intercambia la posición de los dos caracteres antes del cursor, útil para corregir malos tecleos.
+ **Esc+t** : intercambia la posición de las dos palabras antes del cursor, útil para corregir malos tecleos.
+ **Alt+f** : mueve el cursor al inicio de la palabra siguiente de la línea, lo mismo que **Ctrl+right** en la terminal de GNOME.
+ **Alt+b** : mueve el cursor al inicio de la palabra anterior de la línea, lo mismo que **Ctrl+left** en la terminal de
GNOME.
+ **Tab** : autocompleta comandos o rutas de directorios o archivos.
30. **kill -9 [PID]**: Elimina el proceso por una id especificada, tambien se puede hacer tecleando la tecla k al estar en el proceso de top y nos pide el PID y en base a eso podemos acabar con un proceso
31. **ls -lh *.[extension del archivo como .php o .txt etc]** : Lista los archivos que tengan la extension indicada
32. **grep [Archivo dondee buscaremos] -e "Palabra a Buscar Sin // en Regular Expressions"**: Global Regular expresion, busca dentro de un archivo todos los que contengan la expresion indicada, y la salida o resultado tambien se puede guardar en algun tipo de archivo indicado aparte de solo mostrarlo por la consola
33. **grep [Archivo dondee buscaremos] -e "Expresion a buscar" > [nombre de archivo nuevo.extension]** : Guarda la busqueda en un archivo, la busqueda sencible a minusculas o mayusculas pero podemos especificar eso con una expresion regular -i (insensitive)
34. **grep -i [Archivo dondee buscaremos] -e "Expresion a buscar"** : Busqueda insensible a mayusculas o minusculas
35. **grep -i -n [Archivo dondee buscaremos] -e "Expresion a buscar"**: Lista las lineas indicando el numero de donde se encuentra nuestra busqueda
36. **date; grep -i -n [Archivo donde buscaremos] -e "Expresion a buscar" date;** : primero ejecuta date luego la busqueda y luego date de nuevo y asi sabremos cuanto tardo la busqueda en finalizar 
37. **grep -i -n -r [directorio donde buscaremos] -e "Expresion a buscar"** : Busca una palabra en un directorio y en los archivos de dicho direcotrio es decir navega a través de los archivos y carpetas que posea dicho directorio la "-r" indica que sea una busqueda recursiva, es decir que navega en el contenido de los archivos no en el nombre del archivo o carpeta en si
38. **find [./ruta de carpeta/] -name (*).php** : buscar los archivos que coincidan con la extension indicada
39. **find . -name (*).php** : Busca dentro del mismo directorio donde nos encontramos ya que el . hace referencia al lugar donde estamos
40. **curl [enlace de informacion en algun formato]** : Muestra por consola la informacion que contiene el enlace que le pasemos
41. **chmod** : Change Mode Es un comando para cambiar los permisos de un archivo en linux el cual recive como parametro de entrada 3 valores(que hacen referencia a las ternas) y el nombre del archivo\
~~~
chmod 777 -> Estas agregando todos los permisos al owner, al group y al anyone para dicho archivo
chmod 42- -> Estas agregando unicamente permisos de lectura al usuario owner, Tambien agregas unicamente permisos de escritura al group y ningun a anyone
~~~
[esquema de funcionamiento de los permisos de un archivo](img/ternas.png)
42. **printenv o env** : Muestra las varibles de entorno del sistema
43. **echo $[nombre de variable]** : Imprime una variable de entorno o simplemente alguna otra variable
44. **export [nombre de variable] = $PATH** : Crea o inicializa una variable de entorno en este caso igualamos su valor al del path como ejemplo 
45. **bash** : Actualiza tus configuraciones y variables de entorno para no cerrar la terminal
46. **sudo apt install vim** : Instala un paquete en este caso el editor de texto llamado vim como super usuario que hace referencia el comando sudo
47. **sudo** : Es un comando que te permite acceder al las caracteristicas o comandos que quieras ejecutar como super usuario es decir lo que vimos anteriormente de los permisos de las carpetas si ningun usuario tiene por ejemplo permisos de escritura o ejecucion y ejecuto nano o cat con el comando sudo primero nos pedira la contraseña de administrador y luego podremos obtener los permisos para hacer lo que queramos con algun directorio o archivo
48. **vim** : Habre el editor de texto en el cual podemos navegar con una serie de comandos distintos listados a continuación:
+ **:q[+ Enter]** : Nos permite salir de vim hay que escribir los 2 puntos luego una q y presionar enter
+ **vim [nombre de archivo a crear o ejecutar.extension]** : Primero busca dicho archivo y si no lo encuentra entonces lo crea y lo habre 
+ **Modos** : Son indicados en la parte inferior pero normal no es indicado es por defecto
    - Normal : Es para aplicar los comandos pero no texto como en el modo inserccion
    - Insercción : presionando la tecla i para insertar texto con ESC salimos del modo insertar o inserccion, tambien puedes entrar presionando muchos caracteres porque vim detecta que quieres escribir
+ **:w** : Es para guardar las modificaciones hechas a un archivo en el modo inserccion
+ **:edit [nombre o ruta de archivo a editar]**   
+ **h j k l** : Navegacion dentro de un archivo en vim para no ocupar las flechas h es izquierda (opcional presionar numero antes de la letra te mueve la cnatidad de lineas especificadas hacia un lugar especificado)j es abajo k arriba y l derecha
+ **:q!** : Forzar salida sin guardar cambios cuando estamos editando un archivo
+ **:wq** : Guarda y sale del modo inserccion
+ **:x** : wq es decir lo mismo que el comando anterior
+ **:set number** : Enumera las lineas del documento al igual que **:set nu**
+ **tecla 0 y p** : te pone al inicio de la linea y p al final de la linea
+ **w b e** : w = te ubica al inicio de la siguiente palabra, b al inicio de la anterior, e al final de la siguiente palabra
+ **f [mas la letra inicial de alguna palabra que deseo buscar en un archivo de texto]** : Busca dentro del archivo la palabra que comienze por la letra especificada
+ **"*"** : Presionar el asterisco al estar ubicado en una palabra nos llevara a la siguiente aparicion de esa palabra y asi tantas veces como la presionemos
+ **gg** : al presionarlo te lleva a la primera linea del documento
    -Mayus GG te lleva al final de las lineas
    -numero G : numero de linea mas letra g con mayus activado te lleva a la linea especificado


49. **chmod +x(o r o w) arvhico.extension** Asigna permisos de ejecucion lectura o escritura a un usuario a un archivo especifico
50. **rm -f *** : Borra todo los archivos dentro de un directorio 
51. **wich $SHELL** : mostrar donde esta almacenada la shell que estamos usando 
52. **sudo reboot** : Reinicio Reinicia el sistema
53. **sudo dpkg-reconfigure locales** : Cambia el idioma del sistmea y en teclado o keyboard en el lado de distribucion puedes configurar la entrada del teclado
54. ** **
55. ** **
56. ** **
57. ** **
58. ** **
59. ** **
60. ** **
61. ** **
62. ** **
63. ** **
64. ** **
65. ** **
66. ** **
67. ** **
68. ** **
69. ** **
70. ** **
71. ** **
72. ** **
73. ** **
74. ** **
75. ** **
76. ** **
77. ** **
78. ** **
79. ** **
80. ** **
81. ** **
82. ** **
83. ** **
84. ** **
85. ** **
86. ** **
87. ** **
88. ** **
89. ** **
90. ** **
91. ** **
92. ** **
93. ** **
94. ** **
95. ** **
96. ** **
97. ** **
98. ** **
99. ** **
100. ** **
101. ** **
102. ** **
103. ** **
104. ** **
105. ** **
106. ** **
107. ** **
108. ** **
109. ** **
110. ** **
111. ** **
112. ** **
113. ** **
114. ** **
115. ** **
116. ** **
117. ** **
118. ** **
119. ** **
120. ** **
121. ** **
122. ** **
123. ** **
124. ** **
125. ** **
126. ** **
127. ** **
128. ** **
129. ** **
130. ** **
131. ** **
132. ** **
133. ** **
134. ** **
135. ** **
136. ** **
137. ** **
138. ** **
139. ** **
140. ** **