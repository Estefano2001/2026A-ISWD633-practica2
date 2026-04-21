# Redes

Las redes son un componente fundamental que permite la comunicación entre contenedores, así como la comunicación de los contenedores con el mundo exterior.


![Imagen](redes.PNG)

* Bridge: Esta es la red por defecto en Docker. Permite la comunicación entre contenedores en el mismo host. Cada contenedor conectado a la red bridge tiene una IP propia en la subred de la red bridge.

  * Brige por default: Cuando se ejecuta un contenedor, Docker crea automáticamente una red de tipo bridge por default. Esta red se utiliza para permitir la comunicación entre contenedores en el mismo host. Cada contenedor conectado a esta red obtiene su propia dirección IP en la subred de la red bridge.
  * Bridge creada por nosotros: Un usuario también puede crear sus propias redes de tipo bridge en Docker. Esto puede ser útil para organizar y segmentar los contenedores de una aplicación de manera más controlada. Al crear una red bridge personalizada, se puede especificar un rango de direcciones IP y otras configuraciones de red específicas. Los contenedores conectados a esta red utilizarán las direcciones IP de la subred definida por el usuario.
* Host: Con esta red, los contenedores comparten la red del host en lugar de tener su propia interfaz de red. Esto puede mejorar el rendimiento de red, pero los contenedores pueden entrar en conflicto con los puertos del host si intentan utilizar los mismos puertos.
* None: Con esta red, se deshabilita la configuración de red. Los contenedores que usan esta red tienen su propia red de loopback y no pueden comunicarse con otros contenedores a menos que se conecten explícitamente a una red.

### Crear una red de tipo bridge

```
docker network create red1 -d bridge
```

### Crear un contenedor vinculado a una red

```
docker run -d --name contenedor1 --network net-curso01 nginx:alpine
```

### Para saber a qué red está conectado un contenedor

```
docker inspect contenedor1
```

ó

```
docker network inspect net-curso01 
```

### Vincular contenedor a una red

```
docker network connect net-curso01 contenedor1
```

### Para desvincular un contenedor de una red

```
docker network disconnect net-curso01 contenedor1
```

### Para listar las redes existentes

```
docker network ls
```

### Crear los contenedores y las redes que se presentan en el esquema. Usar para todos los contenedores la imagen de nginx:alpine

![Imagen](esquema-ejercicio-redes.PNG)

# COLOCAR UNA CAPTURA DE LAS REDES EXISTENTES CREADAS
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica2/blob/d2957cf5b4203e3a0077c37c4e3e3d168cf1a37f/crearredes.jpeg)

# COLOCAR UNA(S) CAPTURAS(S) DE LOS CONTENEDORES CREADOS EN DONDE SE EVIDENCIE A QUÉ RED ESTÁN VINCULADOS
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica2/blob/07d88e4a29acaea3fc98679634c7bd3103f283ba/net-curso01.jpeg)
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica2/blob/07d88e4a29acaea3fc98679634c7bd3103f283ba/net-curso01.jpeg)
### Para eliminar las redes creadas

```
docker network rm net-curso01 
```

