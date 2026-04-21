### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21
# COMPLETAR
```
docker run -d --name srv-postgres -e POSTGRES_PASSWORD=123456 -e POSTGRES_DB=postgres postgres 
```
### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4
```
docker run -d --name pgadmin -p 8080:80 -e PGADMIN_DEFAULT_EMAIL=admin@admin.com -e PGADMIN_DEFAULT_PASSWORD=admin dpage/pgadmin4 
```
# COMPLETAR

La figura presenta el esquema creado en donde los puertos son:
- a: (8080 (tu navegador = pgAdmin))
- b: (80 (puerto interno de pgAdmin))
- c: (5432 (PostgreSQL interno))

![Imagen](esquema-2-ejercicio.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
# COMPLETAR CON UNA CAPTURA DEL LOGIN
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica2/blob/3c8ea673364cf2aa0e561c8a5deab9e771dc1a98/pgadmin.jpeg)
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica2/blob/3c8ea673364cf2aa0e561c8a5deab9e771dc1a98/pgadmin.jpeg)
### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica2/blob/3c8ea673364cf2aa0e561c8a5deab9e771dc1a98/pgadmin.jpeg)
## Desde el servidor postgresl
### Acceder al servidor
### Conectarse a la base de datos info
# COMPLETAR
### Realizar un select *from personas
# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica1/blob/9deb1db279f90890069e2994a3fbf4abaadc39a7/Lista.jpeg)
