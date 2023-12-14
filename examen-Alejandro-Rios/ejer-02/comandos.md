Construimos la imagen a partir de las modificaciones
```bash
docker build -t insect-app-mod .
```

Ejecucion del contenedor
```bash
docker run -d -p 80:80 --name ejer-02 insect-app-mod
```