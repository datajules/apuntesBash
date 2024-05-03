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


**ls** Nos permite listar los archivos y carpetas del directorio

**pwd** Print working directory. Nos muestra el directorio en donde se encuentra el punetro actualmente.

**touch** Nos permite crear archivos

**cat archivo** Permite ver el contenido de un archivo.

**mdfind** Para buscar archivos funciona solo en macos

