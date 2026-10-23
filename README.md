# Tarea 3.2. Descarga, inspecciona y borra imágenes Docker

**Alumno:** BADR DIBOUNE EL WASMI

## 1. Descargar la imagen Ubuntu 20.04

Descargamos la imagen de Ubuntu desde Docker Hub con el siguiente comando:

```bash
docker pull ubuntu:20.04
```

Para comprobar que se ha descargado correctamente, ejecutamos:

```bash
docker images
```

## 2. Obtener información de la imagen

Utilizamos el comando `docker image inspect` para obtener toda la información de la imagen y guardarla en el archivo `info.txt`.

```bash
docker image inspect ubuntu:20.04 > info.txt
```

Comprobamos que el archivo se ha creado:

```powershell
dir info.txt
```

Para visualizar su contenido, ejecutamos:

```powershell
cat info.txt
```

## 3. Crear un contenedor llamado modulo3

Creamos un contenedor a partir de la imagen Ubuntu 20.04 con el nombre `modulo3`:

```bash
docker create --name modulo3 ubuntu:20.04
```

Para comprobar que el contenedor se ha creado, ejecutamos:

```bash
docker ps -a
```

Este comando muestra todos los contenedores, tanto los que están en ejecución como los que están detenidos.

## 4. Intentar borrar la imagen

Intentamos borrar la imagen con el siguiente comando:

```bash
docker rmi ubuntu:20.04
```

No he podido borrar la imagen `ubuntu:20.04` porque está siendo utilizada por el contenedor `modulo3`. Docker impide eliminar una imagen mientras exista un contenedor que dependa de ella, aunque el contenedor no esté en ejecución.

## 5. Eliminar el contenedor y la imagen

Primero, eliminamos el contenedor `modulo3`:

```bash
docker rm modulo3
```

Después, borramos la imagen de Ubuntu:

```bash
docker rmi ubuntu:20.04
```

Finalmente, comprobamos las imágenes disponibles:

```bash
docker images
```

La imagen `ubuntu:20.04` ya no aparece en la lista, por lo que se ha eliminado correctamente.


## Archivos de la práctica

- `README.md`: documentación de la práctica.
- `info.txt`: información obtenida de la imagen Ubuntu 20.04 mediante `docker image inspect`.
- Capturas de pantalla: evidencias de los comandos y resultados de cada apartado.
