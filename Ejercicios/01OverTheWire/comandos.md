1.- Ver los permisos de un archivo o directorio 
ls -l nombreArchivo-directorio

2.- Output de un comando a nivel de sistema
$(comando) --> ejemplo $(pwd)

3.- asignar permisos a un archivo
chmod o+rw nombre_archivo.extension #o = otros pueden leed y escribir puede ser 
#o --> other
#g --> grupe
chmod o-rw nombre_archivo.extension #otros no pueden leer ni escribir
o con numeros seria
chmod 642 file.txt --> rwx 
es lo mismo que 111
en binario y en binario esto seria --> 7 porque 2 elevado a 2 = 4 mas 2 a 1 = 2 mas 2 a 0 = 1
rwx r-- -w- --> 111 100 010 --> 7 4 2 --> junto chmod 742 

chgrp nombre_usuario archivo.extension #Asigno a un usuario dentro de los grupos de un archivo

4. Permisos especiales 
lsattr -> enumera los permisos especiales de un archivo
chattr +i -V file.txt --> asigna permisos especiales
-V es para ver un registro visual del comando aplicado

5.- ver nombre de usuario donde estamos
whoami

6.- Ver el path completo donde estamos
$PATH

7.- tiempo de computo
time antes de un comando para ver cuanto se demora en ejecutar

8.- 
+ Busca un archivo de tipo file\
`find . type -f`
+ Busca archivos leibles, escribibles y executables
~~~
find . type -f -readable -writable -executable 
~~~
+ para la negacion de un comando o el contrario podriamos aplicar un signo de exclamación con el comando anterior seria
~~~
find . type -f ! -readable ! -writable ! -executable 
~~~
+ Busca por tamaño de archivo o directorio depende de que escribas en los parametros
~~~
find . type -f -readable ! -executable -size 1033c //Para decir que son bytes especificar una c
~~~

9. **CTRL + R** --> Es un tipo de buscador de los comandos que ya escribimos y nos muestra los posibles autocompletados al lado derecho de la linea de comandos



