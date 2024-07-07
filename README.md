
# Hoja de referencia rápida de comandos básicos de Linux

## Operaciones con directorios
- **Crear un directorio**: `mkdir`
- **Cambiar de directorio de trabajo**: `cd`
- **Consultar cuál es el actual directorio de trabajo**: `pwd`
- **Borrar un directorio**: `rmdir`
- **Consultar el contenido del directorio**: `ls`, `tree`

### `mkdir`
Crea directorios y opcionalmente puede ponerles los permisos.

**Sintaxis**:
```sh
mkdir [opción...] directorio...
```

**Ejemplo**:
```sh
$ mkdir ~/tmp
```

**Opciones**:
- `-p` : Crea también los directorios de la ruta que no existan.
- `-m permisos` : A la vez que crea el directorio le pone los permisos especificados.
- `-v` : Modo verboso.

**Ejemplo**:
```sh
$ mkdir -m a+rxw tmp
$ ls -ld tmp
drwxrwxrwx 2 usuario usuario 4096 ago 30 18:23 tmp
```

### `cd`
Cambia el directorio de trabajo.

**Ejemplo**:
```sh
$ cd
```

**Cambiar a un directorio específico**:
```sh
$ cd ../tmp
```

**Cambiar al directorio anterior**:
```sh
$ cd -
```

**Usando CDPATH**:
```sh
$ mkdir -p ~/tmp/{a/{d,e},b,c}
$ tree ~/tmp
$ CDPATH=~/tmp
$ cd a
$ cd b
$ cd d
$ cd a/d
```

### `pwd`
Muestra la ruta absoluta del directorio de trabajo.

**Ejemplo**:
```sh
$ pwd
/home/usuario/tmp
```

### `rmdir`
Borra directorios vacíos.

**Ejemplo**:
```sh
$ rmdir  ~/tmp/a/d  ~/tmp/c
```

**Eliminar directorios y directorios padre**:
```sh
$ rmdir -p ~/tmp/a/{d,e}
```

### `ls`
Muestra el contenido del directorio.

**Sintaxis**:
```sh
ls [opción...] [ { fichero | directorio }... ]
```

**Ejemplo**:
```sh
$ ls
$ ls -a
```

**Lista en formato largo**:
```sh
$ ls -l
```

**Mostrar el directorio en sí mismo**:
```sh
$ ls -ld tmp
```

**Mostrar números de inodo**:
```sh
$ ls -i carta*
```

**Mostrar tiempo de acceso**:
```sh
$ ls -lu carta*
```

**Mostrar tiempo de cambio**:
```sh
$ ls -lc carta*
```

**Excluir archivos por patrón**:
```sh
$ ls -I '*.txt'
```

**Ordenar por versión**:
```sh
$ ls -v car*
```

**Otras opciones útiles**:
- `-R` : Listado recursivo.
- `-S` : Ordenar por tamaño.
- `-X` : Ordenar por extensión.
- `-t` : Ordenar por tiempo de modificación.
- `-r` : Orden inverso.
- `-h` : Tamaños legibles por humanos.
- `-k` : Mostrar tamaños en kilobytes.
- `-m` : Listado separado por comas.
- `-n` : Mostrar UID y GID numéricos.
- `-A` : Listar todo excepto . y ..
- `-B` : Excluir archivos de respaldo que terminan en ~.
- `--full-time` : Mostrar fecha y hora completas.

### `tree`
Muestra el contenido del directorio en forma de árbol.

**Instalar**:
```sh
# aptitude install tree
```

**Ejemplo**:
```sh
$ tree tmp
```

**Mostrar archivos ocultos**:
```sh
$ tree -a tmp
```

**Mostrar solo directorios**:
```sh
$ tree -d tmp
```

**Mostrar rutas completas**:
```sh
$ tree -f tmp
```

**Opciones útiles**:
- `-L nivel` : Nivel máximo de profundidad a mostrar.
- `-P patrón` : Mostrar archivos que coincidan con el patrón.
- `-I patrón` : Excluir archivos que coincidan con el patrón.
- `--prune` : Excluir directorios vacíos.
- `--noreport` : Omitir el resumen final.
- `-p` : Mostrar permisos.
- `-u` : Mostrar usuario.
- `-g` : Mostrar grupo.
- `-s` : Mostrar tamaño.
- `-D` : Mostrar tiempo de modificación.
- `-t` : Ordenar por tiempo de modificación.
- `-r` : Orden inverso.

## Operaciones con archivos
- **Crear un archivo vacío**: `touch`
- **Borrar un archivo**: `rm`
- **Mostrar el contenido de un archivo**: `cat`

### `touch`
Crear un archivo vacío o actualizar los tiempos de acceso y modificación.

**Ejemplo**:
```sh
$ touch nombre_archivo
```

### `rm`
Borrar archivos o directorios.

**Ejemplo**:
```sh
$ rm nombre_archivo
```

**Forzar borrado y recursivo**:
```sh
$ rm -rf directorio
```

### `cat`
Mostrar el contenido de un archivo.

**Ejemplo**:
```sh
$ cat nombre_archivo
```

**Redirigir salida**:
```sh
$ cat nombre_archivo > nuevo_archivo
```

**Añadir a la salida existente**:
```sh
$ cat nombre_archivo >> archivo_existente
```

### `mv`
Mover o renombrar archivos y directorios.

**Ejemplo**:
```sh
$ mv origen destino
```

### `cp`
Copiar archivos y directorios.

**Ejemplo**:
```sh
$ cp origen destino
```

**Copia recursiva**:
```sh
$ cp -r directorio_origen directorio_destino
```

**Preservar atributos**:
```sh
$ cp -a origen destino
```

