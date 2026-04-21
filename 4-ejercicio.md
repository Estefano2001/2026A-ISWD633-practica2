## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
# COMPLETAR
```
docker network create net-wp 
```
### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# COMPLETAR
```
docker run -d --name mysql --network net-wp -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_DATABASE=wordpress -e MYSQL_USER=wpuser -e MYSQL_PASSWORD=wp123 mysql:8 
```
### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR
```
docker run -d --name wordpress --network net-wp -p 9300:80 -e WORDPRESS_DB_HOST=mysql -e WORDPRESS_DB_USER=wpuser -e WORDPRESS_DB_PASSWORD=wp123 -e WORDPRESS_DB_NAME=wordpress wordpress 
```
De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es **(a: 9300,
80: puerto interno de WordPress)**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica2/blob/2f412c6f97a2aaa8c0a3cd97d7c31775ffe56718/configuracioncompleta.jpeg)
Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica1/blob/9deb1db279f90890069e2994a3fbf4abaadc39a7/Lista.jpeg)
### Eliminar el contenedor wordpress
# COMPLETAR

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?

#### El contenido del sitio web se mantiene, ya que los datos se almacenan en el contenedor de MySQL. WordPress solo actúa como interfaz, mientras que la base de datos persiste en el contenedor de MySQL dentro de la red net-wp.
# COMPLETAR
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica1/blob/9deb1db279f90890069e2994a3fbf4abaadc39a7/Lista.jpeg)
