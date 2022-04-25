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
32. **grep [Archivo dondee buscaremos] -e "Expresion a buscar"**: Global Regular expresion, busca dentro de un archivo todos los que contengan la expresion indicada, y la salida o resultado tambien se puede guardar en algun tipo de archivo indicado aparte de solo mostrarlo por la consola
33. **grep [Archivo dondee buscaremos] -e "Expresion a buscar" > [nombre de archivo nuevo.extension]** : Guarda la busqueda en un archivo, la busqueda sencible a minusculas o mayusculas pero podemos especificar eso con una expresion regular -i (insensitive)
34. **grep -i [Archivo dondee buscaremos] -e "Expresion a buscar"** : Busqueda insensible a mayusculas o minusculas
35. **grep -i -n [Archivo dondee buscaremos] -e "Expresion a buscar"**: Lista las lineas indicando el numero de donde se encuentra nuestra busqueda
36. **date; grep -i -n [Archivo donde buscaremos] -e "Expresion a buscar" date;** : primero ejecuta date luego la busqueda y luego date de nuevo y asi sabremos cuanto tardo la busqueda en finalizar 
37. **grep -i -n -r [directorio donde buscaremos] -e "Expresion a buscar"** : Busca una palabra en un directorio y en los archivos de dicho direcotrio es decir navega a través de los archivos y carpetas que posea dicho directorio la "-r" indica que sea una busqueda recursiva, es decir que navega en el contenido de los archivos no en el nombre del archivo o carpeta en si
38. **find [./ruta de carpeta/] -name *.php** : buscar los archivos que coincidan con la extension indicada
39. **find . -name *.php** : Busca dentro del mismo directorio donde nos encontramos ya que el . hace referencia al lugar donde estamos
40. ** **