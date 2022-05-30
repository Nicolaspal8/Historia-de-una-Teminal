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
+ Aplicar cat a una lista de archivos devueltos en el comando anterior
~~~
find . type -f -readable ! -executable -size 1033c | xargs cat
~~~
+ Aplicar un formateo de outpu con xargs en este caso el archivo si tiene muchos espacios lo formatea y lo entrega limpio solo con el contenido leible 
~~~
find . type -f -readable ! -executable -size 1033c | xargs cat | xargs
~~~
+ Sustituir o eliminar ciertos caracteres con tr 
~~~
find . type -f -readable ! -executable -size 1033c | xargs cat | tr -d '\n' //Elimina saltos de linea
tr -d '\t' //Elimina tabulador
~~~
+ Utilizar Expresiones regulares con sed para Borrar o Remplazar cosas
~~~
find . type -f -readable ! -executable -size 1033c | xargs cat | sed 's/\n//g' 
- Sustituye saltos de linea por nada de manera global
- Sustituye tabulado --> sed 's/\t//g' 
~~~
+ Trabaja con el output de otro comando como cat para formatear textos
~~~
- muestrame la primera linea --> cat C:\Users\archivo | head -n 1
- muestrame la 2 ultimas lineas --> cat C:\Users\archivo | tail -n 2
- muestrame la linea 2 --> cat C:\Users\archivo | awk 'NR==2'

- sustituye la primera palabra en el output de un archivo de la primera linea 
--> cat C:\Users\archivo | head -n 1 | sed 's/Caracteres/NuevosCaracteres/'

- sustituye todas las palabras es decir de manera global 
--> cat C:\Users\archivo | head -n 1 | sed 's/Caracteres/NuevosCaracteres/g'

- busca con grep dentro de un archivo las lineas que "Empiezen" con una palabra o caracter en especifico 
--> cat C:\Users\archivo | grep "^palabra"

- sustituye una palabra o caracter y lo que le sigue por otra 
--> find . -type f ! -executable -readable -size 1033c | xargs cat | sed "s/^ *//" //Espacios sustituidos y lo que sigue por nada

- busca palabras que empiezen en un criterio y terminen en otro 
--> grep "/^hola$/"

- elimina todo lo que comienze con espacio y termine en nada o espacio 
--> find . -type f ! -executable -readable -size 1033c | xargs cat | sed "/^\s*$/d"

- dime la linea donde esta cierta palabra o caracter dentro de un texto 
--> grep "/^hola$/" -n

- muestrame lo que hay en una linea en especifico
--> awk 'NR==1923'

- muestrame todo a partir de la raiz que tenga un usuario y un grupo especifico y solo muestrame las operaciones exitosas y solo los que pesen 33 bytes
--> find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
~~~

9. **CTRL + R** --> Es un tipo de buscador de los comandos que ya escribimos y nos muestra los posibles autocompletados al lado derecho de la linea de comandos

10. **disown o disown -a** --> Independizar procesos para que al cerrar la consola no se cierre lo que no quieres y no dependa de esa consola en ejecucion y cree su propio espacio de ejecucion 

11. **Cuentame las lineas de un archivo**
--> cat archivo | wc -l
- Cuentame los caracteres --> cat archivo | wc -c


12. 

