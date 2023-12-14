Instalación de NGINX
```bash
docker pull nginx
```

Ejecucion del contenedor con la aplicacion como volumen
```bash
docker run -d -p 80:80 -v $(pwd)/insect-game:/usr/share/nginx/html --name mi-servidor-web nginx
```