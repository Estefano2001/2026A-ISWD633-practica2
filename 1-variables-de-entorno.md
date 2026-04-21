# Variables de Entorno
### ¿Qué son las variables de entorno?

#### Son valores almacenados en el sistema operativo que las aplicaciones pueden usar para configurarse sin necesidad de modificar su código
# COMPLETAR

### Para crear un contenedor con variables de entorno

```
 docker run -d --name srv-nginx8 nginx:alpine -e username=estefano -e role=admin
```
### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

# COMPLETAR
# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica2/blob/792f4106f7b5030b145272bd64d86331e49e4c6b/variables%20de%20entorno.jpeg)

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# COMPLETAR
```
  docker run -d --name srv-mysql mysql -P
```
### ¿El contenedor se está ejecutando?

#### No se esta ejecutando 
# COMPLETAR

### Identificar el problema

#### Ingresamos el comando, docker logs srv-mysql, con esto identificamos el problema con el contenedor. Necesitamos especificar al menos una de estas variables de entorno: 
- MYSQL_ROOT_PASSWORD
- MYSQL_ALLOW_EMPTY_PASSWORD
- MYSQL_RANDOM_ROOT_PASSWORD
# COMPLETAR

### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### ¿Qué bases de datos existen en el contenedor creado?
![image alt](https://github.com/Estefano2001/2026A-ISWD633-practica2/blob/6779e1c02f1d80f59c55fe045a311a090bb1078f/databases.jpeg)

# COMPLETAR
