# Utiliza la imagen oficial de Nginx
FROM nginx:latest

# Elimina el archivo de configuración predeterminado de Nginx
RUN rm /etc/nginx/conf.d/default.conf

# Copia los archivos de la aplicación al directorio de trabajo de Nginx
COPY asteroids-game-master/ /usr/share/nginx/html

# Exponer el puerto 80 para acceder a la aplicación
EXPOSE 80

# Comando para iniciar Nginx en primer plano
CMD ["nginx", "-g", "daemon off;"]
