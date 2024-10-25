---

# Comandos Docker

![Imagen de Docker](Files/image.png)

## Descargar Imágenes
Para descargar imágenes, visita: [Docker Hub](https://hub.docker.com/).

```bash
sudo docker pull <imageToDownload>
```

## Ver Imágenes Descargadas
```bash
sudo docker images
```

## Ver Procesos en Ejecución
```bash
sudo docker ps
sudo docker ps -a
```

---

## Construir una Imagen a partir de un Dockerfile
```bash
sudo docker build -t <nombre-del-proyecto> .
```

## Crear una Imagen de un Proyecto con Puerto
```bash
sudo docker run -it -p <puertoExpuesto>:<puertoApp> <nombreImagen> --name <nombreContenedor>
```

## Crear una Imagen para Reflejar Cambios en el Código
```bash
sudo docker run -it --name <nombreDeLaImagen> -p 5173:5173 -v /ruta/a/tu/proyecto:/src/app <nombreContenedor>
```

---

## Ejecutar un Contenedor
```bash
sudo docker start <nombreContenedor>
```

## Ver Logs de un Contenedor
```bash
sudo docker logs -f <nombreContenedor>
```

## Ver Detalles de un Contenedor
```bash
sudo docker inspect nombre_contenedor
```

---

## Crear un Contenedor de PostgreSQL
Descargar la imagen de PostgreSQL:
```bash
docker pull postgres
```

Crear y ejecutar el contenedor:
```bash
sudo docker run --name <nombreContenedor> -e POSTGRES_USER=<nombreUsuario> -e POSTGRES_PASSWORD=<contrasena> -e POSTGRES_DB=<nombreDeBaseDatos> -d -p 5432:5432 postgres
```

Ver contenedores:
```bash
sudo docker ps -a
```

Iniciar el contenedor:
```bash
sudo docker start <nombreContenedor>
```

Acceder al contenedor:
```bash
sudo docker exec -it <nombreContenedor> bash
psql -U <nombreUsuario> -D <nombreDeBaseDatos>
```
