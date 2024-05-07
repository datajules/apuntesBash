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


## Procesos

```bash
jobs
ps
./sleeper.sh &
fg 1
```

Cuando añadimos *&* mandamos la instrucción de ejecutar el proceso en segundo plano. Para regresar a ese proceso podemos usar *fg 1*


```bash

```