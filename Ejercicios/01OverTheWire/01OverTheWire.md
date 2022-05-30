1. **Nivel 1** --> 
Usamos ssh para conectarnos a la maquina con un puerto en especifico
~~~
ssh user_name@host -p puerto
password --> boJ9jbbUNNfktd78OOpsqOltutMc3MY1
~~~
2. **Nivel 2** -->
El nombre de - (guion) de un archivo debe ser accedido de otra forma porque al usar cat lo considera como espera de parametros por ende para leer el contenido del archivo escritos en guiones puede ser como
~~~
cat ./- --> Accedemos a el a través del directorio
cat /home/ruta/- --> Accedemos a el a través de la ruta principal
cat /home/ruta/* -->Lista todo lo que hay interno
cat $(pwd)/- --> Lo que hará es lo mismo que el anterior de home/ruta/- pero le pasamos la ruta como una variable
password --> CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
~~~
3. **Nivel 3** --> Este archivo tiene espacios por ende escribimos 
1.- entre comillas el nombre 
2.- las iniciales y tabulamos
3.- cat sp* Habrira todo que empieze por sp
4.- cat *me Abrira lo que termine en me 
5.- cat *this* Abrira lo que tenga entremedio la palabra this
6.- Como es el unico archivo podemos escribir cat *
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
4. **Nivel 4** --> La clave esta en un directorio oculto por ende lo accedemos median ls -a o ls -la en forma mas ordenada que haga una lista de los ficheros en el directorio
tambien podemos utilizar 
1.- find para mostrar de forma recursiva todo lo que hay en adelante de donde estamos como find .
2.- find . -type f -printf "%f\t%p\t%u\t%g\t%m\n" | column -t
find = busca
. = en este directorio en adelante
-type f = tipos file
-printf = y muestrame por
%f = archivos
\ = indicar que muestre de forma tabulada
t%p = luego muestrame la ruta absoluta
t%u = el usuario propietario del archivo
t%g = grupo asignado
t%m = modo de permiso asignado a nivel numerico como rwx
| column -t = muestra todo mas ordenado en forma de columna mas legible visualmente
3.- find . -name .hidden --> Busca en el directorio actual en adelante un archivo llamado .hidden y nos muestra la ruta de acceso
4.- find . -name .hidden | xargs cat --> xargs sirve para ejecutar comandos luego del output del comando anterior es decir que ejecutara un cat en la ruta que devuelva el comando find . -name -hidden
password --> pIwrPrtPN36QITSp3EQaw936yaFoFgAB
5. **Nivel 5** --> Archivo solo humanamente legible 
find . -name -file* (buscara todo los que comiencen con file)
ahora que sabemos donde buscar debemos aplicar el comando file para saber que tipo de archivo hay dentro de cada directorio y para hacer esto mezclaremos el comando de find con xargs y asi aplicar el comando a cada uno de los archivos dentro del directorio

find . -name -file* | xargs file
y luego un cat al archivo que sea humanamente leible que sera de tipo ASCII text
cat inhere/-file07

mejoras --> si aplicamos el comando time antes del find veremos que tarda mas que si lo hacemos con el comando file inhere/* es decir que me diga de que tipo son todos los archivos dentro de la carpeta inhere de una vez sin usar find y xargs
o tambien podriamos usar cat $(find . -name -file07) lo cual me da la ruta y leugo le aplica el cat
password --> koReBOKuIDDepwhWk7jZC0RTdopnAYKh


6. **Nivel 6** --> Fichero humanamente legible, 1033bytes, no ejecutable
find . -type f -readable ! -executable -size 1033c | xargs cat | xargs
busca --> 
directorio actual --> 
tipo file --> 
archivos leibles --> 
no ejecutables --> 
de 1033 bytes --> 
al output aplica un cat (muestrame el contenido) --> 
formateame el output sin espacios de manera mas legible 

Otra Forma --> find . -type f ! -executable -readable -size 1033c | xargs cat | sed "s/^ *//" sustituye el comienzo de un espacio y lo que le sigue por nada 
password --> DXjZPULLxYr17uwoI01bNLQbtFemEgo7

7. **Nivel 7** --> en algun lugar del servidor con user bandit7 y grupo bandit6 con un peso de 33bytes

find / -user bandit7 -group bandit6 -size 33c 2>/dev/null | xargs cat 

buscar a partir de la raiz --> algo con usuario bandit7 --> y grupo bandit6 --> con un peso de 33 bytes --> y solo muestrame las operaciones exitosas omite los errores --> luego el resultado de la ruta de ese archivo aplicale un cat es decir muestrame el contenido

password --> HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

8.- **Nivel 8** --> Buscar dentro de un archivo junto a la palabra millionth 
Usamos grep para buscar dentro de un archivo\
cat archivo | grep 'millionth'

Otra forma--> 
- grep -i data.txt -e "millionth" busqueda insensitive (Da igual mayuscula o minuscula)
- grep '/millionth/' data.txt
- awk '/millionth/' data.txt
Observacion --> 
 - Al usar grep con cat no es necesario usar -e de expresion a buscar pero al usar sol grep es necesario
 - grep acepta expresiones regulares pero sin los // es decir solo hace falta envolver todo en comillas
 - La mas optima es usar solo grep sin cat asi consumimos menos recursos
password --> cvX2JJa4CFALtqS87jk27qwqGhBM9plV

9. **Nivel 9** --> La contraseña es la unica que no se repite en un archivo lleno de caracteres

--> sort archivo.txt  | uniq -u



password --> UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR