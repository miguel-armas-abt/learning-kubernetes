# CONFIGURACIÓN

[← Regresar a notas](../../README.md) <br>

----

> ### ⚙️ Instalar Docker Desktop (Windows)
> Referencias:
>   - [Instalar WSL2 y Docker](https://youtu.be/OGtLAMUyDrc?si=CPrSn975qjKHZISX)
>   - [Activar virtualización en la BIOS](https://youtu.be/FJIOvB4Jy0w?si=JW5HP5eaaFchWF2y)
> 

> ### ⚙️ Asignar recursos a Docker Desktop
> Cree un archivo `.wslconfig` en la ruta `C:\Users\<username>\`, añada el siguiente contenido según los recursos de su computadora y reinicie Docker Desktop.
> ```javascript
> [wsl2]
> memory=3072MB
> processors=5
> ```

> ### ▶️ Mostrar información de Docker
> ```shell script
> docker info
> ```

> ### ▶️ Eliminar todos los recursos sin utilizar (imágenes, contenedores, volúmenes y redes)
> - Utilice `--all`para especificar a todos los recursos, incluyendo los que están actualmente en uso
> ```shell script
> docker system prune --all
> ```