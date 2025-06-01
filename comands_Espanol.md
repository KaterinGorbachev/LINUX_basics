## Listar 

- comando para listar solo las directorios en el directorio actual 

  ls -d */


- listar archivos mostrando el tamano en formato legible para humanos

  ls -lh


- listar todos los archivos incl. ocultos en formato detallado

  ls -la


- listar archivos ordenados por fecha de modificacion (los mas recientes primero)

  ls -t


- listar recursivamente el contenido de un directorio y sus subdirectorios

  ls -R


- listar archivos en orden inverso

  ls -r


- listar el contenido del directorio raiz

  ls /


- listar el contenido del directorio que esta 2 niveles por encima del actual

  ls ../..


- listar el contenido del directorio home del usuario actual

  ls ~


- listar archivos en formato de una solo columna

  ls -1


- listar todos los archivos que coincidan con un patron

  ls *


- redirigir la salida del comando ls a un archivo llamado output.txt

  ls > output.txt


- mostrar info detallada de un archivo especifico

  ls -l archivo.txt


---

## Operaciones sobre archivos


- crear un archivo vacio
 
  touch archivo.txt


- crear varios archivos con nombres secuenciales del 2 al 5

  touch archivo{2..5}


- crear un directorio llamado "SOM" y dentro de el otro directorio "Practicas" en una solo operacion

  mkdir -p /SOM/Practicas


- crear varios directorios a la vez

  mkdir dir1 dir2 dir3  


- crear una secuencia de directorios

   mkdir nombre_directorio{2..10}


- mostrar el contenido de un archivo

  cat archivo.txt


- ver el contenido del archivo /etc/passwd

  cat /etc/passwd


- ver el contenido del archivo /etc/shadow

  cat /etc/shadow 


- ver los permisos del archivo /etc/shadow

  ls -l /etc/shadow

  
- eliminar un archivo

  rm fichero


- eliminar el directorio y todo su contenido

  rm -r nombre_directorio


- eliminar un archivo de forma forzada 

  rm -f nombre.txt


- eliminar un directorio vacio

  rmdir nombre_directorio


- eliminar varios directorios

  rm -r nombre_directorio{2..4}


- copiar un archivo a un directorio destino

  cp /ruta_directorio/file.txt /ruta_nuevo_directorio


- copiar un directorio y todo su contenido a otro directorio

  cp -r /ruta_completa/nombre_directorio /ruta_completa/otro_directorio


- copiar todos los archivos que empiezan por "ej" al directorio SOM

  cp ej* ./SOM


- copiar todos los archivos que empiezan por "ej" seguido de 1 solo caracter al directorio SOM

  cp ej? ./SOM


- mover un archivo de un directorio a otro

  mv ../dir1/text.txt ../otro_directorio


- renombrar un directorio

  mv nombre_directorio nuevo_nombre


- renombrar un archivo

  mv nombre_archivo nuevo_nombre


- mover un archivo a un directorio especifico

  mv archivo.txt /home/usuario


- editar un archivo

  nano nombre_archivo
  vi nombre_archivo


- crear un enlace duro a un archivo

  ln archivo.txt enlace_nombre


- crear un enlace simbolico a un archivo

  ln -s archivo.txt enlace_nombre


- determinar el tipo de un archivo

  file archivo.txt


- ver el contenido de un archivo pagina por pagina

  more fichero_nombre


- buscar un patron en un archivo

  grep patron fichero


- buscar la cadena md5 en el archivo ignorando mayusculas y minusculas

  grep -i 'md5' archivo.txt


- mostrar un mensaje en la terminal

  echo mensaje


- escribir un texto en un archivo

  echo texto > archivo_nombre


- anadir un texto al final de un archivo

  echo texto >> archivo_nombre



---

## Usuarios y los permisos 


- crear un nuevo usuario

  sudo useradd nombre_usuario


- establecer una contrasena para el usuario mortadelo

  sudo passwd mortadelo


- eliminar un usuario

  sudo userdel nombre_usuario


- mostrar la informacion de ID del usuario actual

  id


- mostrar la informacion de ID del usuario root

  id root


- buscar informacion sobre un usuario especifico en la base de datos del sistema

  getent passwd mortadelo 

- cambiar al usuario mortadelo

  su mortadelo 


- crear un nuevo usuario con directorio home y contrasena

  sudo useradd -m -p filemon
  

- crear un nuevo grupo

  sudo groupadd grupo


- anadir un usuario a un grupo

  sudo adduser usuario grupo


- anadir un usuario al grupo sudo

  sudo adduser usuario sudo 


- eliminar un usuario de un grupo

  sudo deluser usuario grupo 


- cambiar recursivamente los permisos de todos los archivos y directorios

  chmod -R 744 *
  

- establecer el bit SGID en un directorio

  chmod g+s /nombre_directorio


- cambiar el propietario de un archivo

  chown pepa nombre_archivo


- cambiar el propietario y el grupo de un archivo

  chown pepa:nuevo_grupo nombre_archivo


- cambiar el propietario de un directorio y todo su contenido de forma recursiva

  chown -R pepe


- cambiar solo el grupo de un archivo

  chown :pepe fichero
  chgrp new_group_nombre fichero


- anadir un usuario a un grupo adicional sin eliminar sus grupos actuales

  sudo usermod -a -G grupo_nombre user_nombre


- dar permisos de ejecucion al propietario de un archivo

  chmod u+x archivo_nombre
  

- establecer permisos de lectura, escritura y ejecucion para el propietario, y lectura y ejecucion para grupo y otros

  chmod 755 archivo_nombre


- dar permisos de escritura al propietario y al grupo

  chmod ug+w archivo.txt
  
  
- quitar permisos de escritura al grupo y establecer de lectura y ejecucion para otros en el directorio /proyectos/ads

  chmod g-w, o=rx /proyectos/ads


- dar permisos totales solo al propietario de un archivo

  chmod 700 archivo.txt


- dar permisos de lectura y ejecucion solo al propietario

  chmod u+rx archivo
  chmod 500 archivo


- dar permisos de lectura, escritura y ejecucion al propietario, y solo lectura al grupo y otros para todos los archivos del directorio actual

  chmod 744 *


--- 

## Sistema y otros comandos

- mostrar el directorio de trabajo actual

  pwd


- cambiar al directorio home del usuario actual

  cd ~


- comando para subir un nivel en la estructura de directorios

  cd ..


- cambiar a un subdirectorio llamado "algo" en el directorio actual

  cd ./algo


- mostrar y configurar la fecha y hora del sistema

  timedatectl
  

- limpiar la pantalla de la terminal

  clear


- salir de la terminal o de una sesion

  exit


- mostrar la fecha y la hora actuales

  date


- mostrar un calendario

  cal


- apagar el sistema

  shutdown


- apagar el sistema inmediatamente

  shutdown -h now 


- mostrar el espacio disponible en los sistemas de archivos en formato legible

  df -h


- acceder el manual de un comando

  man nombre_comando


- ver los procesos en ejecucion en tiempo real

  top


- ver todos los procesos en ejecucion

  ps aux


- terminar un proceso especifico

  sudo kill -q numero_proceso


- instalar un paquete

  sudo apt install nombre_paquete 


- reiniciar el sistema

  sudo reboot


- ver historial de comandos ejecutados

  history


- repetir el ultimo comando con privelegios de superusuario

  sudo !!


- mostrar la info sobre las interfaces de red

  ip a
  

- mostrar la tabla de enrutamiento

  ip r


- comprobar la conectividad con otro host

  ping


- instalar el servidor SSH

  sudo apt install ssh


- verificar el estado del servicio SSH

  sudo systemctl status ssh.service

- generar un par de claves SSH

  ssh -keygen


- conectarte a un servidor ssh en modo verbose

  ssh -v
  

- mostrar informacion detallada sobre el sistema operativo

  uname -a
  

- mostrar info sobre el nombre de host

  hostnamectl








  
  
  

  

  
