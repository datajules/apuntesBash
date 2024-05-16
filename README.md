# apuntesBash

## Terminología:

**shebang**: La primer línea de un script indica el interprete que se debe emplear para ejecutar el script. Para esto se utiliza el par de caracteres *!#*, también denominado *shebang*.

```bash
#!/bin/bash
echo "Hello World"
``` 

**Chmod**: Es un comando que cambia los permisos de acceso al directorios o archivos. Se emplea para hacer a los scripts ejecutables.

```bash
chmod +x myscript.sh
``` 

**alias**: Nos permite abreviar líneas con muchas instrucciones o comandos muy largos. Estos alias se configuran en el archivo *.bashrc*.

```bash
alias lm='ls -al | more'
``` 

**export:**: Permite disponer de las variables entre distintas sesiones y *child processes* Se emplean para llamar cosas como las API key.

```bash
export DB_PASSWORD='mysecurepass'
``` 

**find**: Es un comando para encontrar archivos y folders.

```bash
find . -name "*.py"
```

**linux shell**: Consiste en la terminal que permite ejecutar comandos de linux.

**Bash script**: Es un *script* escrito en Bash y que usualmente tiene la terminación *.sh* y esta compuesto por comandos de bash.

**Environment variable** Es una variable glogal disponible para todos los shells y procesos.

```bash
# Shebang indicating Bash interpreter
#!/bin/bash

# Print hello world 
echo "Hello World"

# Set an environment variable
export MY_VAR="some value"

# Print the variable
echo $MY_VAR

# Define an alias
alias ll="ls -l"

# Use the alias 
ll
``` 

Para conocer el sistema operativo que se está ejecutando

```bash
uname -a
```

Para el uso que se le está dando al disco:

```bash
du -h
du -sh
```

Para ver archivos y directorios con más detalle 

```bash
du ls -lah
```



**ls** Nos permite listar los archivos y carpetas del directorio

**pwd** Print working directory. Nos muestra el directorio en donde se encuentra el punetro actualmente.

**touch** Nos permite crear archivos

**cat <archivo>** Permite ver el contenido de un archivo.

```bash
cat readme.txt
less readme.txt
```

**mdfind** Para buscar archivos funciona solo en macos

**date**: Nos devuelve la fecha actual

**df** Uso del disco, con la opción -h  para que brinde más datos
```bash
df -h
```

**top** Nos da un panorama del uso del sistema

La arquitectura básica de un comando de bash es la siguiente:

*cmd - option target

Por ejemplo:

```bash
ls -lah /tmp
```

Para conocer todos los comandos disponibles de bash 

```bash
cd /usr/bin
ls -l
```


**Wich** Muesta la ubicación exacta de un archivo o directorio

```bash
wich python
```


## Modificar archivos y directorios


```bash
touch newfile.txt
mkdir newdir
mkdir -p moredir/dir1/dir2
rm -rf moredir
mv newfile.txt newdir/
```

**mv** Sirve tanto para mobver como para renombrar archivos

**mkdir -p** Nos permite crear múltiples directorios al mismo tiempo, es decir directorios y subdirectorios

**rm -rf** Elimina todo el contenido de un directorio.

**wc** Cuenta caracteres, parabras y líneas de archivos.


## Procesos

```bash
jobs
ps
./sleeper.sh &
fg 1
```

Cuando añadimos *&* mandamos la instrucción de ejecutar el proceso en segundo plano. Para regresar a ese proceso podemos usar *fg 1*

## Shell piping works

Para conectar la salida de un comando con la entrada de otro empleamos el símbolo de pipe **|**

```bash
ls -l | wc -l
```

Para redirecciónar el resultado de un comando a un archivo, en lugar de a la salida de la consola podemos usar **>**.

```bash
ls -l > output.txt
```

Si se quiere agregar contenido modificando un archivo en lugar de sobreescribirlo se puede usar **>>**
```bash
echo "¡Hola mundo!" > output.txt
```


Ejecución condicionada. Se ejecuta el siguiente comando únicamente si el primero se ejecutó con éxito.

```bash
ls <file> && echo "File exists"
```

*[ -f <archivo>]* Es una prueba condicional que muestra si un archivo existe o no.

*sort -r* nos permite ordenar las líneas
```bash
ls -l | sort -r
```

En cambio *grep* devuelve solo las líneas con el término señalado


```bash
ls -h | grep p
```

Para mostrar el contenido de un log que se va reescribiendo:

```bash
tail -f /var/log/dpkg.log
```

Para ver un determinado número de líneas
```bash
tail -n 3 /var/log/dpkg.log
```
Tal como existe *tail*, también es posible emplear *head* para ver el comienzo del log. 

```bash
head -n 3 /var/log/dpkg.log
```

Para seleccionar líneas de forma aleatoria usamos

```bash
shuf -n 100 nba_2017.csv
```


Podemos combinar un comando como *history* con *less* para poder recorrer con las arroy todos los comandos que hemos ejecutado en la terminal

```bash
history | less
```

Otra buena combinación que podemos hacer es buscar un comando en el histórico que contenga un término en específico empleando comandos que ya hemos visto:

```bash
history | grep head
```

Otra forma de invocar comandos de history es mediante la marca *!* Porejemplo se puede indicar el comando que quiere ser invoado

```bash
!2
```

Si lo que se desea es invocar el últico comando ejecutado se emplea *!!*:

```bash
!!
```

## Secure Shell (SSH)

El **SSH** es un protocolo que otorga un tunel de comunicación seguro entre dos sistemas. Permite crear un tunel encriptado, ejecución remota de comandos, y protección de los puertos.

Las **SSH Keys** Son las claves públicas o privadas empleadas para autenticar y asegurar las comunicaciones entre dos sistemas sin la necesidad de emplear pasword.

El **Git** es un sistema distribuido de control de versiones que permite trakear cambiosen el código soportando múltiples desarrolladores.

En cambio **GitHub** Es una plataforma basada en la nube basada en Git que permite el desarrollo coordinado de proyectos.

El **Por Forwarding** Es una técnica que permite redireccionar las conexiones de red entrantes en un puerto *IP* de una máquina a otra.

**ssh-keygen** Genera una key que puede ser usada en la autenticación SSH.


**ssh-L hanilita el puerto 8080 del host remoto para alojar la conexión.

```bash
# Generate public/private SSH key pair
ssh-keygen -t rsa -b 4096 -C "myemail@example.com"  

# Print the generated public key 
cat ~/.ssh/id_rsa.pub

# Clone a GitHub repo via SSH 
git clone git@github.com:user/repo.git

# Port forward remote port 8080 to local port 8080
ssh -L 8080:localhost:8080 user@remotehost
```

Para crear una variable en donde alojar cosas como el ip usamos *export*:

```bash
export HOST = "54.89.238.83"
echo $HOST
```

Para conectarse a un servidor remoto

```bash
# Generate SSH Key Pair
ssh-keygen -t rsa -b 4096

# SSH Remote Connection
ssh username@remote_host 

# Port Forwarding
ssh -L 8888:remote_host:80 username@remote_host
```

**SSH**: Habilita un tunel encriptado para enviar comandos y recibir o enviar archivos a un servidor remoto. Permite manejar extensiones remotas de forma local. También nps permite debugeear nuestras aplicaciones alojadas directamente en un host remoto.



```bash
# Creamos una SSH key
ssh-keygen -t rsa
# Mostramos la credencial
cat /home/ec2-user/.ssh/id_rsa.pub
```

La copiamos a github.

Ahora podemos crear un nuevo repo y clonarlo vía ssh.

Es posible crear alias para los documentos, sobre todo cuando los vamos a usar seguido.

```bash
alias documents="cd ~/Documents"
documents 
```

Para cargar y ejecutar un script o archivo en el bash:

```bash
source ~/.bashrc
```

Las variables globales, pueden ser usadas dentro de los scipts

```bash
export API_KEY="credencial" 
python script.py 
```

Para crear ambientes virtuales en python empleamos el comando venv seguido por el archivo a crear.
Posteriormente source lo ejecuta. Este comando puede agregarse dnetro de  ~/.bashrc para cargarlo desde que se lanza la terminal.

```bash
python3 -m venv ~/.venv
source ~/.venv/bin/activate
```
La mayor parte de los ambientes de configuración tienen un  *~/.bashr* que permite automatizar la configuración.

Para saber en dónde está instalado el Bash Shell:

```bash
echo $SHELL
```

## Shell variables

Una *Shell variable* es una variable que solo existe y almacena datos que serán usados en scripts o en procesos.

```bash
saludo="Hola"
echo $saludo
echo $saludo "¿Cómo estás?"
```
Para hacerla accesible por *child shells* y *child processes* se emplea *export*.

```bash
export saludo="hola"
bash
echo $saludo
```

Para correr un script en el *shell* actual se usa **source** de esta forma todas sus variables y alias estarán disponibles en el ambiente.

```bash
source ./script.sh
echo $saludo
```

De esta forma tantppo procesos *Parebnt y child* procces pueden emplear variables vía *export*.

```bash
export saludo="Hola"
bash
echo "Soy un child - $saludo"
```
 Para acceder a las variables vía Python
```bash
 import os
 print(os.environ['saludo'])
```

Las *shell variables* nos permiten almacenar datos para usarlos en scripts y procesos.


## Flujos de datos

Para guardar información en un archivo empleamos *>*.

```bash
ls -l > listaArchivos.txt
```

Para manejar datos que se ingresan desde otros programas o bien del usuario:

```bash
read -p "¿Cómo te llamas? " name
echo "Hola $name"
```

Por lo regular cuando un programa o función arroja información, esta es manipulada por otros procesos por medio de pipes *|*.

```bash
echo -e "gato\nperro\ngato" | sort | uniq -c
```
 Otra operación común es administrar los errores que arrojan los programas almacenando las salidas. Para eso usamos *2* que hace referencis al error estandar.

```bash
ls -l invalid 2> error.txt
```

En caso de que queramos omitir la muestra de errores podemos enviarlo a */dev/null*

```bash

```

Para transponer una string usamos *rev*

```bash
echo 1993 | rev
```

El comando *chmod +x* en Bash se utiliza para agregar permisos de ejecución a un archivo.


```bash

```
