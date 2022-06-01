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


12. **awk**
- muestrame el argumento 1 --> awk '{print $1}
- muestrame el argumento 2 --> awk '{print $2}
- muestrame el ultimo elemento de la linea donde estoy 
--> awk '/millionth/' data.txt | awk 'NF{print $NF}'
- revierte una cadena y muestrame la primera cadena
--> awk '/millionth/' data.txt | rev | '{print $1}'


13. **cut**
- muestrame lo que este a la izquierda del primer caracter que encuentres 
--> cut archivo.txt -d 'caracter' -f 1
--> cut archivo.txt -d 'caracter' -f 2 //A la derecha

14. **sort uniq**
- Uniq necesita previamente un ordenamiento para trabajar sobre un archivo o palabras por eso va en conjunto de sort

- ordena alfabetimacemente un archivo
--> sort archivo 
- ordename y muestrame solo las palabras o secuencia de caracteres unicos
--> sort archivo.txt  | uniq -u

15. **strings**
- Lista los caracteres imprimibles y es bueno para buscar dentro de los caracteres reconocibles de un archivo

--> strings archivo.txt
- otro ejemplo seria usar el resultado en conjunto con grep
--> strings archivo.txt | grep "caracteres"

16. **!$**
- Hace referencia al ultimo archivo trabajado o directorio y en base a eso puedes trabajar con el

17. **Bucle en bash**
- Una forma de crear scripts es crear un archivo con el codigo y luego ejecutar el archivo 
a nivel de archivo -->
~~~
contador=1 #En bash al declarar una variable hay que escribirla pegada sin espacio entre los operando

while read line; do 
        echo "Linea $contador: $line"
        let contador+=1 
done < /ruta del archivo donde se aplicara el script
~~~
- a nivel de CLI (Interfaz de Linea de comandos) con un ejemplo del ejercicio -->
~~~
contador=1; strings data.txt  | grep "===" | while read line; do echo "Linea $contador $line; contador+=1; done
~~~

18. **tr** 
- Similar a sed permite eliminar o sustituir textos, a diferencia de sed la expresion se aplica automaticamente a todo si no le decimos lo contrario en sed habria que anteponer una s en la regular expresion de sustitucion y luego una g que se haga de manera global
**Otro punto importante es que tr trabaja por caracter como si decimos tr 'root' 'nueva' todas las r la sustituye por n la primera o por u y asi sucesivamente


- sustituye los espacios por saltos de linea --> archivo tr ' ' '\n'
- hace una rotacion a partir de la posicion 13 incluyendo minusculas y mayusculas
--> cat archivo.txt | tr '[G-ZA-Fg-za-f]' '[T-ZA-St-za-s]'
abcdefghijqlmnopqrstuvwxyz

19. **xxd**
- Permite trabajar con formatos de archivos hexadecimales y transformarlos o revertirlos

- crea un archivo hexadecimal a partir de otro --> 
a partir de un archivo puedes crear un hexadecimal xxd archiv_normal > nuevo_opcional(si no lo imprime por consola y no guarda el resultado del hexadecimal creado)

- a partir de un echo puedes crear un hexadecimal y guardarlo en otro archivo nuevo y volverlo a comprimir
--> echo "contenido del archivo"  | xxd > nuevo archivo

- puedes comprimir varias veces un archivo a hexadecimal y luego hacer lo mismo reversivamente para optener el resultado inicial 
--> xxd archivo | xxd | xxd > archivo_final

- transforma un archivo normal y solo muestrame los bytes sin los hexadecimales (ojo que si quiero aplicar este comando xxd -ps sobre un archivo ya hexadecimal debo primero aplicar un -r tantas veces como sea necesario y luego usar el -ps ya que esto primero lo pasa a hexadecimal y luego extrae solo los bytes es decir no formatea por si solo un archivo ya hexadecimal extrayendo los datos) 
--> xxd -ps archivo_normal > resultado (es opcional guardar el resultado si no solo lo mostrara por consola) 

- si el archivo ya es un hexadecimal --> cat archivo | xxd -r  | xxd -ps 



