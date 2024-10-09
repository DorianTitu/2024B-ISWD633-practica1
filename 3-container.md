# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine

```
 docker create --name svr-web nginx:alpine
```

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world

```
docker create hello-world  
```

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 

```
docker start svr-web
```

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](img/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine

```
docker run --name svr-web2 nginx:alpine
```

**¿Qué sucede luego de la ejecución del comando?**

Crea y ejecuta un contenedor basado en la imagen nginx:alpine.

Asigna el nombre svr-web2 al contenedor.

Si la imagen no está en local, Docker la descarga.

Nginx corre en el contenedor, pero no se exponen puertos al host sin -p.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine

```
docker run -d --name svr-web3 nginx:alpine
```

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```

Eliminar el contenedor que se creó a partir de la imagen hello-world 

```
docker rm c75586e73324409cb85479bd3467bfb617d3a34bb316782e4565b887f87dd33f
```

Verificar que el contenedor que se eliminó

```
docker rm -f svr-web3
```

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```

Eliminar el contenedor **srv-web3** 

```
docker rm -f svr-web3
```

Verificar que el contenedor que se eliminó

```
docker rm -f svr-web3
```

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
# COMPLETAR
