Construir imagen
```bash
docker build -t insect-app-mod:latest .
```

Etiquetar imagen
```bash
docker tag insect-app-mod:latest pikatostes/insect-app-mod:latest
```

Subir la imagen
```bash
docker push pikatostes/insect-app-mod:latest
```