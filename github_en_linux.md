# GIT Y GITHUB

En este apartado empezaremos a utilizar tanto git como github en nuestro sistema operativo linux.

## Creación de par de claves SSH

Para empezar tendremos que crearnos un par de claves. Para ello entraremos en nuestra terminal y tendremos que entrar en la siguiente ruta:

~~~
$ cd ~/.ssh
~~~

A continuación crearemos nuestra par de claves con el siguiente comando:

~~~
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/schacon/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/schacon/.ssh/id_rsa.
Your public key has been saved in /Users/schacon/.ssh/id_rsa.pub.
The key fingerprint is:
43:c5:5b:5f:b1:f1:50:43:ad:20:a6:92:6a:1f:9a:3a
~~~

Una vez creada podremos copiar el contenido del archivo y pegarlo en nuestra cuenta github. Para ello tendremos que poner el siguiente comando y copiar el contenido.

~~~
$ cat ~/.ssh/id_rsa.pub 
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAklOUpkDHrfHY17SbrmTIpNLTGK9Tjom/BWDSU
GPl+nafzlHDTYW7hdI4yZ5ew18JH4JW9jbhUFrviQzM7xlELEVf4h9lFX5QVkbPppSwg0cda3
Pbv7kOdJ/MTyBlWXFCR+HAo3FXRitBqxiX1nKhXpHAZsMciLq8V6RjsNAQwdsdMFvSlVK/7XA
t3FaoJoAsncM1Q9x5+3V0Ww68/eIFmb1zuUFljQJKprrX88XypNDvjYNby6vw/Pb0rwert/En
mZ+AW4OZPnTPI89ZPmVMLuayrD2cE86Z/il8b+gw3r3+1nKatmIkjn2so1d01QraTlMqVSsbx
NrRFi9wrf+M7Q==
~~~

## Configuración y edición de ficheros mediante terminal

Una vez copiado entramos en github y nos dirigimos a settings --> SSH and GPG keys --> New SSH key, una vez en la nueva pestaña en key pegamos lo copiado y en name pondremos el nombre que queramos para identificar esa clave.

Cuando hayamos guardado la clave en github crearemos un repositorio y al crearlo nos dará una URL en https, pero tendremos que seleccionar la URL ssh.

Copiada la URL nos dirigimos a nuestra terminal y instalamos git con el comando:

~~~
$ sudo apt-get install git
~~~

Y a continuación clonamos los repositorios en nuestro ordenador.

~~~
git clone git@github.com:usuario/repositorio.git
~~~

Tendremos que  especificar el nombre y el correo de nuestro git para ello nos vamos al repositorio y tendremos que añadir los siguientes comandos.

~~~
$ git config --global user.name "Nombre Apellido"
$ git config --global user.email correoelectronico@gmail.com
$ git commit --amend --reset-author
~~~

Podemos crear y añadir un fichero, siendo el primer paso crearlo en nuestro ordenador y despues sincronizarlo con Github para ello tendremos que ejecutar el comando de creción de fichero.

~~~
$ echo "Prueba">prueba.txt
~~~

Una vez creado lo sincronizamos con nuestro Github.

~~~
$ git add prueba.txt
$ git commit -m "He creado el fichero prueba.txt"
$ git push
~~~

Con el primero comando lo introducimos a Github, con el segundo le introducimos un comentario(Hay que introducir siempre un comentario) y con push guardamos esos cambios.

Podremos modificar el nombre de un fichero o modificar tambien el contenido.
Para modificar el nombre del fichero lo podremos hacer de la siguiente manera.

~~~
$ git mv prueba.txt prueba2.txt
$ git commit -am "He cambiado el nombre del fichero"
$ git push
~~~

Para modificar el contenido entraremos con el "nano" o cualquier editor que tengamos instalado, cambiaremos lo que queramos. Guardamos y lo subiremos de nuevo con los comando.

~~~
$ git add prueba2.txt
$ git commit -am "He creado el fichero prueba.txt"
$ git push
~~~

Si queremos borrar algun fichero de nuestro repositorio Github.

~~~
$ git rm prueba2.txt
$ git commit -am "He borrado el fichero prueba2"
$ git push
~~~

Podemos ver el estado de nuestro github por la temrinal.

~~~
$ git status
~~~

prueba.