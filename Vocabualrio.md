# Vocabulario de la Terminal

1. **Terminal** : Una terminal en un comienzo era una maquina fisica que nos permitia comunicarnos con el computador a travez de un output de tarjetar perforadas, hoy en día la conocemos como la interfaz de linea de comandos o (CLI comand line interface) que emula las caracteristicas de una terminal la cual nos permite interactuar con el computador o microprocesador que recibe las instrucciones a travez de texto es decir una serie de instrucciones, tambien nos permite navegar entre los directorios de nuestro arbol de directorios interno y además comunicarnos con programas que no poseen una interfaz grafica en si
+ Nos permite velocidad a la hora de ejecucion de codigo ya que es una interfaz dedicada a recibir texto y mostrarlo por ende es una interfaz super ligera
2. **Arbol de directorios**![](img/arbol%20de%20directorios%20de%20un%20sistema%20basado%20en%20linux%20Ubuntu.png)
3. **Historial de comandos** : Almacena todos los comandos ingresaros en la terminal globalmente no importa si ya la habias cerrado
4. **cd /usr/bin/** : En Ubunto es el lugar donde se almacenan los comandos como en system en windows
5. **comando** : Un comando es un puqueño codigo encapsulado en un ejecutable u llamado cada vez que escribimos su nombre lo que es llamado tambien como mnemoticos es una forma de referenciar una secuencia o una accion en especifico de manera resumida ya que dicha instruccion es interpretada en binario por el computador o microprocesador que la lee
6. **Bashrc y Bash_profile** : Es el script de shell que ejecutamos cada vez que iniciamos sesion y nos permite controlar cosas como colores o alias de comandos en la terminal, este script se encuentra oculto en el home es decir en el perfil donde estamos logeados o iniciados  el cual contiene una serie de configuraciones para la terminal pero solo para la sesion
+ Bash_profile: Se ejecuta para los inicios de sesion a diferencia de bashrc que se ejecuta para los shells interactivos sin inicio de sesion,n bash_profile se ejecuta para configurar el shell antes del simbolo del sistema inicial
7. **ls -lha** : Muestra los archivos ocultos en un listado
8. **PID** : Process ID es el id del proceso es decir que perfil o usuario lo esta ejecutado
9. **PR** : Prioridad de algun proceso en ejecucion al ser habierto con el comando top
10. **$** : en la interfaz de comandos que emula la terminal el dolar es indicativo que tenemos acceso o permiso de tipo usuario
11. **#** el hastag indica que tenemos acceso de administrador o super usuario
12. **Archivos .csv** : 
13. **Ternas** : Son los que definen el nivel de acceso que tenemos a algun tipo de directorio o archivo compuesto por generalmente un archivo se divide en 3 ternas la primera hace referencia a los permisos del owner el segundo de los grupos y el tercero a anyone a cualquiera y cada letra osea el simbolo del permiso que tiene alguna entidad sobre algun directorio esta compuesto por valores En cuanto a terminos Binarios dichos valores sirven para determinar el permiso para cada usuario o entidad:
+ **r** : Leer tiene el Valor de = 2² -> 4
+ **w** : Escribir tiene el Valor de = 2¹ -> 2
+ **x** : Ejecutar tiene el Valor de = 2↑0 -> 1
+ **-** : Valor = 0
+ **Posibles combinaciones**
    - **rwx : 7** --> Tiene Permisos de lectura, escritura y ejecución
    - **rw- : 6** --> Tiene Permisos de lectura y escritura No de ejecución
    - **r-- : 4** --> Unicamente de lectura
    - **-w- : 2** --> Unicamente de Escritura
    - **--x : 1** --> Unicamente de ejecucion
    - **r-x : 5** --> Lectura y ejecución
    - **--- : 0** --> No tiene ningun permiso
14. **Variables de Entorno** : Almacena los valores de configuracion de informacion del sistema o shell etc, del funcionamiento importante para el equipo y sirve como mapa para el sistema operativo sepa donde estan
15. **PATH** : Almacena la ruta de los binarios del sistema para ser ejecutados al ser llamados
16. **Binario** : Dentro del sistema operativo cuando se habla de binarios son los programas que se encargan de realizar una tarea y son ejecutados por el sistema operativo y cada vez que ejecutamos un comando como ls o pwd se encuentra en una direccion dentro de nuestros directorios y es un binario que cuando se accede a el se es ejecutado, podemos conocer la ubicacion de cada comando con el comando **wich**
17. **Script** : Basicamente es un conjunto de codigo o secuencia de comandos, instrucciones el cual tiene una funcion en especifica a ejecutar por el sistema, en shell generalmente los scripts no se compilan, es decir que no pasan por el proceso de creacion de un archivo binario ejecutable para ser interpretado por el computador
+ Son identificados en los encabezados por #!/bin/bash (O la ruta de donde se encuentra tu shell en este caso seria bash)
18. **Prompt** : Es el caracter o conjunto de caracteres en una linea de comandos que demuestra que esta a la espera de ordenes para ser ejecutadas 
19. **vim** : Es un editor de texto de la linea de comandos que posen los dispositivos GNU/Linux que tambien puede ser ejecutado en windows si tienes la bash instalada
20. **ssh** : es un protocolo para transferir informacion de un computador a otro el cual funciona con un modelo Cliente Servidor, los datos son enviados de una forma mas segura con una key que solo conoce el cliente y servidor 
21. **Telnet** : Tambien es un protocolo de comunicacion entre dos equipos pero a diferencia que es en texto plano y es mas vulnerable a ataques informaticos
22. **Origen Cruzado en funciones potentes** : Es un tipo de seguridad que se implementa para proteger procesos significativos de un sistema o programa el cual abarca muchos otros conceptos
    + **COEP** : Politica de incrustacion de origen cruzado\
     es un mecanismo que permite que se puedan solicitar recursos restringidos (como por ejemplo, las tipografías) en una página web desde un dominio diferente del dominio que sirvió el primer recurso.1​ Una página web podría libremente incrustar imágenes, hojas de estilo, scripts, iframes y vídeos de origen cruzado.2​ Ciertas peticiones de origen cruzado, más notablemente peticiones Ajax, están prohibidas por defecto por la política de seguridad del mismo origen (en inglés, same-origin security policy).\
     CORS define una forma en la cual el navegador y el servidor pueden interactuar para determinar si es seguro permitir una petición de origen cruzado.3​ Esto permite tener más libertad y funcionalidad que las peticiones de mismo origen, pero es adicionalmente más seguro que simplemente permitir todas las peticiones de origen cruzado. La especificación para CORS fue originalmente publicada como una recomendación de la W3C4​ pero dicho documento se encuentra obsoleto.5​ La especificación actual mantenida activamente que define CORS es el estándar Fetch (en inglés, Fetch Living Standard)6​ del WHATWG.
    + **Origen** : Se refiere a la url o dominio de donde se hace una peticion
    + **COOP** : Politica de apertura de origen cruzado
    + **CORP** : Politica de recursos de origen cruzado
    + **CORS** : Uso compartido de recursos de origen cruzado Quiere decir que es un concepto implementado por los navegadores en las cabeceras o headers el cual no permite que el servidor le muestre informacion a un dominio no permitido en dicho servidor, es decir un usuario esta en un dominio realiza una peticion al servidor el servidor comprueba si el dominio de origen de la peticion esta admitido en el servidor y en base a eso el navegador dice 200 ok o niega el acceso y no realiza la peticion de los datos, ya que se basa en una primera comprobacion de seguridad y luego de eso procede a hacer la peticion de los datos 
    + **CORB** : Bloque de lectura de origen cruzado
    + **SOP**  : Same Origin Policcy es la politica de seguridad del mismo origen es el concepto por defecto que emplean los navegadores y basicamente dice que el navegador impide que se cargen datos a un dominio diferente del cual se encuentra un usuario, es decir que los datos deben proveenir de la misma fuente, pero el problema esta en cuanto navegamos a otro sitio web y es malicioso el cual hace una peticion al servidor por ejemplo de la aplicacion del banco y lo hace a través de del dominio del banco pero con  las cookies almacenadas en nuestro navegador por ender el navegador cree que todo esta ok ya que la peticion se hace a través de la direccion de dominio presente en el servidor y se esta haciendo una peticion de origin cruzado donde el que solicita la informacion no es el dominio principal y para eso tenemo CORS
23. ** **
24. ** **
25. ** **
26. ** **
27. ** **
28. ** **
29. ** **
30. ** **
31. ** **
32. ** **
33. ** **
34. ** **
35. ** **
36. ** **
37. ** **
38. ** **
39. ** **
40. ** **