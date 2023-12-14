Servidores web con Docker:
1. Lanzar contenedor con servidor web Nginx:
```bash
docker run -d -p 80:80 --name nginx-container nginx
```
- -d: Ejecutar el contenedor en segundo plano.
- -p 80:80: Mapear el puerto 80 del host al puerto 80 del contenedor.
- --name nginx-container: Asignar un nombre al contenedor.
- nginx: Nombre de la imagen de Nginx.
2. Parar y borrar el contenedor Nginx:
```sh
docker stop nginx-container
docker rm nginx-container
```
3. Lanzar contenedor Nginx mapeando un directorio del host:
```bash
docker run -d -p 80:80 -v /ruta/local:/usr/share/nginx/html --name nginx-container nginx
```
- -v /ruta/local:/usr/share/nginx/html: Mapear un directorio local al directorio de documentos web del contenedor.
4. Lanzar segundo contenedor Nginx usando un puerto diferente:
```bash
docker run -d -p 8080:80 --name nginx-container2 nginx
```
- -p 8080:80: Mapear el puerto 8080 del host al puerto 80 del contenedor.
5. Lanzar contenedor con servidor web Apache:
```bash
docker run -d -p 8080:80 --name apache-container httpd
```
6. Lanzar contenedor Apache mapeando un directorio del host:
```bash
docker run -d -p 8080:80 -v /ruta/local:/usr/local/apache2/htdocs --name apache-container httpd
```
7. Lanzar contenedor con servidor web con PHP:
```bash
docker run -d -p 80:80 -v /ruta/local:/var/www/html --name php-container php:apache
```
8. Lanzar servidor con BD MySQL:
```bash
docker run -d -p 3306:3306 --name mysql-container -e MYSQL_ROOT_PASSWORD=password mysql
```
- -e MYSQL_ROOT_PASSWORD=password: Establecer la contraseña de root para MySQL.
9. Acceder a la consola MySQL del contenedor:
```bash
docker exec -it mysql-container mysql -p
```
Multicontenedor con Docker Compose:
10. Crear fichero docker-compose para base de datos y gestor:
```yaml
version: '3'
services:
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: password
  adminer:
    image: adminer
    ports:
      - 8080:8080
```
11. Crear fichero docker-compose para WordPress:
```yaml
version: '3'
services:
  wordpress:
    image: wordpress
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_PASSWORD: password
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: password
```
12. Añadir entrada y tema nuevo a WordPress:
Accede a http://localhost:8080 en tu navegador.<br>
Configura WordPress con los detalles de la base de datos.<br>
Añade una entrada y un tema nuevo.<br>
13. Detener y borrar los contenedores de WordPress:
```bash
docker-compose down
```
14. Reiniciar el servicio y comprobar la persistencia:
```bash
docker-compose up -d
```