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

- Observaciones --> Utilizamos sort para luego trabajar con uniq -u que recibe un archivo o grupo de caracteres ordenados y asi puede trabajar sobre el, uniq posee mas herramientas las cuales se pueden ver con man uniq o uniq --help o en la documentacion de coreutils de gnu en la pagina web
password --> UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

10. **Nivel 10** --> La contraseña esta antecedida de los unicos caracteres legibles como signo de = 

- Primero hay que extraer los caracteres legibles del archivo con strings y luego sobre el output podremos aplicar un script de busqueda como grep o awk y como nos dicen que esta precedido de signos == osea mas de uno aplicamos ese parametro de busqueda a grep

strings archivo.txt | grep "==="
Otra Forma de hacer aplicando lo que hemos aprendido hasta aqui en base al output y a su formato que es este
~~~
========== the*2i"4
========== password
Z)========== is
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
~~~
--> strings data.txt | grep "===" | tail -n 1 | cut -d ' ' -f 2 
muestrame los caracteres imprimibles --> buscame los que contengan === --> muestrame la ultima linea --> formateame el texto a partir del primer espacio y muestrame el conjunto que sigue
**Ejemplo Brutal**
~~~
contador=1; strings data.txt | grep "===" | while read line; do echo "Linea $contador: $line";let cont
ador+=1; done
//Output -->
Linea 1: ========== the*2i"4
Linea 2: ========== password
Linea 3: Z)========== is
Linea 4: &========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
~~~
password --> truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

11. **Nivel 11** --> La contraseña esta encriptada con base64
- Si vemos en el comando de informacion base64 --help veremos que utilizando base64 -d (decode) file_name.extension decodificaremos el archivo

--> base64 -d data.txt

password --> IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

12. **Nivel 12** --> La contraseña esta en un archivo de texto al cual hay que aplicarle una rotacion de 13 posiciones incluyendo minusculas y mayusculas
- Para leer el archivo usaremos cat y en conjunto usaremos tr
- Vemos que el archivo empieza por la letra G luego en la rotacion contamos cual es el caracter luego de 13 posiciones en el alfabeto americano
--> cat data.txt | tr '[G-ZA-Fg-za-f]' '[T-ZA-St-za-s]' 


password --> 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu


13. **Nivel 13** --> Contraseña en archivo comprimido multiples veces en hexadecimal y luego usando diversos compresores

- como el archivo esta comprimido varias veces y no sabemos en especifico a que tipo de archivo resultara la descompresion final o en el transcurso entonces usaremos un descompresor universal llamado 7z juto con el parametro l que hara una vista previa de la ejecucion de descompresion 

- muestrame la vista previa de lo que harás si descomprimieras un archivo
--> 7z l archivo.gzip
- descomprime un archivo 
--> 7z x archivo

- como son multiples archivos crearemos un scrip en bash para que a través de una bucle descomprima todas las veces que sea necesario

touch descompresor.sh
chmod +x descompresor.sh o !$ (que toma en cuenta el ultimo archivo manipulado)
nano descompresor.sh para escribir en el archivo
ahora escribiremos el siguiente codigo
~~~
#!/bin/bash #Para indicar que shell usaremos

nombre_descomprimido=$(7z l data.hex | grep "Name" -A 2 | tail -n 1 | awk 'NF{print $NF}' ) #Es para sacar el nombre si esque el archivo se puede descomprimir

7z x data.hex > /dev/null 2>&1 #Redirijimos los errores al dev null para que no se impriman en consola

while true; do
    7z l $nombre_descomprimido > /dev/null 2>&1 #Redirijimos errores o algun output en consola para que no molesten en cada iteracion
    if [ "$(echo $?)" == "0" ]; then #Preguntamos si el codigo de estado del comando ejecutado anteriormente es diferente de exitoso (0) porque eso significara que ya no se puede descomprimir
        descomprimido_siguiente=$(7z l $nombre_descomprimido | grep "Name" -A 2 | tail -n 1 | awk 'NF{print $NF}' )
        7z x $nombre_descomprimido > /dev/null 2>&1 && nombre_descomprimido=$descomprimido_siguiente #Hacemos esto para que si se ejecuta el primer comando entonces el segundo dira que ahora estara trabajando sobre el siguiente archivo generado al descomprimirser el anterior
    else
        cat $nombre_descomprimido
        exit 1 #Aplicamos un codigo de estado diferente de 0 para que no entre de nuevo en el bucle y este termine
    fi
done
~~~
- Usaremos una herramienta (7z descompresor universal) la cual la podemos instalar en linux con el siguiente comando --> sudo apt-get install p7zip-full p7zip-rar
- La sintaxis en bash debe ser perfecta por ejemplo acabo de tener un error de 15 minutos que era porque luego del if debe haber un espacio y luego la condicion 


- cat data.txt | xxd -r 
ejemplos --> xxd de un archivo lo transforma a hexadecimal y si le aplico un xxd -r lo reviero a forma anterior 
password --> 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

14. **Nivel 14** -->

15. **Nivel 15** -->

16. **Nivel 16** -->

17. **Nivel 17** -->

18. **Nivel 18** -->

19. **Nivel 19** -->

20. **Nivel 20** -->

21. **Nivel 21** -->

22. **Nivel 22** -->

23. **Nivel 23** -->

24. **Nivel 24** -->

25. **Nivel 25** -->

26. **Nivel 26** -->

27. **Nivel 27** -->

28. **Nivel 28** -->

29. **Nivel 29** -->

30. **Nivel 30** -->

31. **Nivel 31** -->

32. **Nivel 32** -->

33. **Nivel 33** -->