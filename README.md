# Desplegar-dos-servicios-con-Docker-Swarm--volumenes

1)- Primero creo dos carpetas Apache y node, apache tendra index.php y su Dockerfiles. Lo mismo sera para la carpeta node

2)- Afuera de estas carpetas tendra que estar la bd en este caso datos.sql y el docker-compose.yml configurar segun corresponda

3)- Despues hago el siguiente comando:

```bash
    docker build . -t "servicio-node" 
```

--> posicionarse en la carpeta de node en este caso y darle un nombre en donde estan las ""

4)- Lo mismo para apache:

```bash
    docker build . -t "servicio-apache"
```

5)- Se debe instalar en node express y mysql o mysql2

6)- Luego de esto hacer docker:

```bash
    docker swarm init 
```

7)- Luego:

```bash
    docker stack deploy -c docker-compose.yml "mis-servicios" 
```    

--> posicionarse en la carpeta que contiene el .yml

8)- En caso que se apague y se prenda o se cree mucho contenedores se puede usar

    docker service logs "services_node"  

    Este comando te dara el error que tiene el servicio

9)- Para apagar todos los servicios se puede utilizar

```bash
    docker swarm leave --force
```

10)- Si se utiliza este comando se tiene que volver a repetir el proceso, pasos 6 y 7.

11)- Para ejecutar el tp seguir el paso 10 # Desplegar-dos-servicios-conDocker-Swarm--volumenes
# Desplegar-dos-servicios-con-Docker-Swarm--volumenes
