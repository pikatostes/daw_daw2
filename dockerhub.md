Para subir una imagen a Docker Hub, sigue estos pasos:

Crea una cuenta en Docker Hub:
Si aún no tienes una cuenta en Docker Hub, ve a Docker Hub y crea una cuenta.

Inicia sesión en Docker Hub:
Abre tu terminal y ejecuta el siguiente comando para iniciar sesión en Docker Hub. Serás solicitado a ingresar tu nombre de usuario y contraseña de Docker Hub.

```bash
docker login
```
Construye tu imagen:
Asegúrate de que tu imagen de Docker esté construida localmente en tu máquina. Cambia al directorio donde está tu Dockerfile y ejecuta el siguiente comando para construir la imagen. Reemplaza nombre_de_la_imagen y etiqueta con tu propio nombre e etiqueta de imagen.

```bash
docker build -t nombre_de_la_imagen:etiqueta .
```
Etiqueta tu imagen:
Etiqueta tu imagen con el nombre de usuario de Docker Hub para que pueda ser subida correctamente. Reemplaza nombre_de_usuario con tu nombre de usuario en Docker Hub y nombre_de_la_imagen y etiqueta con los valores que usaste al construir la imagen.

```bash
docker tag nombre_de_la_imagen:etiqueta nombre_de_usuario/nombre_de_la_imagen:etiqueta
```
Sube la imagen a Docker Hub:
Ejecuta el siguiente comando para subir tu imagen a Docker Hub. Esto subirá la imagen etiquetada al repositorio correspondiente en tu cuenta de Docker Hub.

```bash
docker push nombre_de_usuario/nombre_de_la_imagen:etiqueta
```
Verifica en Docker Hub:
Visita Docker Hub en tu navegador web y verifica que tu imagen haya sido subida correctamente.