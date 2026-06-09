**Nivel: Básico**

Iniciamos con un escaneo de puertos abiertos:

![[01- Primer escaneo.png]]

hacemos un escaneo de servicios  a los puertos abiertos:

![[02- Segundo escaneo.png]]

Observamos que el puerto 80  nos ofrece un servicio http y nos dirigimos a el.

![[03-Pagina principal.png]]

Lanzamos gobuster en busca de directorios ocultos:

![[04- Escaneo Gobuster.png]]

Entre otros conseguimos el directorio PANEL y UPLOADS:

![[Panel Upload.png]]

este directorio nos permite subir archivos lo que hace sensible a la pagina a la inserción de archivos que puedan comprometerla. Como la pagina del index es PHP podemos probar con un archivo malicioso en PHP con una Reverse Shell para conseguir acceso a la maquina. Buscamos código para este fin en Internet.

![[05- Rshell PHP.png]]

Este pude servirnos. Después de descargarlo mi primer paso fue renombrarlo a un nombre mas corto:

![[06- Renombro el archivo.png]]

lo editamos para colocar nuestra ip Tun0 y el puerto que elijamos para recibir la reverse Shell:

![[07- Edicion de ip rshell.png]]

Intentamos subirlo a la pagina sin éxito puesto que no nos  permite subir archivos con la extensión PHP. Pero no esta todo perdido.

![[08- PHP no permitido.png]]

Podemos utilizar el archivo con alguna extensión que nos permita y se pueda ejecutar en la web.


![[Cambio de extencion.png]]

Para tal fin renombre el archivo y cambie su extensión a .PHP5

![[Seleccionamos el archivo a subir.png]]

Seleccionamos el archivo a subir.

![[Subiodo con exito.png]]

Ahora si pudimos subirlo con éxito. 

Vemos el escaneo de Gobuster para localizar donde se aloja el archivo que subimos y damos con la carpeta UPLOADS. 

![[Directorio uploads.png]]
 Vemos que efectivamente se encuentra allí pero antes de hacer un click para ejecutarlo nos aseguramos de estar en escucha por el puerto seleccionado con NETCAT:

![[netcat en escucha.png]]

Ahora si podemos hacer click a ver si nos da una shell de la maquina victima:

![[consegimos la reverse shell.png]]

Efectivamente funciono. Resta hacer el tratamiento de tty correspondiente  para obtener una shell totalmente interactiva:

script /dev/null -c bash 
cotrol Z
stty raw -echo; fg
reset xterm
export TERM=xterm
export SHELL=bash

Con la shell ahora interactiva buscamos nuestro user.txt e intentaremos luego escalar privilegios de ROOT.

![[Conseguimos la user.png]]

Ahora si a escalar privilegios. Buscamos binarios con permisos SUID para ver si alguno nos permite escalar privilegios.

![[Buscamos binarios con permisos SUID.png]]

![[binario python suid.png]]


El PYTHON es uno de los sospechosos así que vamos a intentarlo.

![[Escalamos con python.png]]

Aquí nos movemos al directorio donde se encuentra el binario y ejecutamos esa linea de la imagen.

![[Conseguimos la root.png]]

Ya siendo usuario ROOT nos dirigimos al directorio de este usuario donde habitualmente se encuentra nuestro objetivo para poder terminar el desafío.