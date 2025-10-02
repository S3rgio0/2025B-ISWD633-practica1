# Imagen
### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
# COMPLETAR
<img width="645" height="154" alt="imagen" src="https://github.com/user-attachments/assets/bf9442e6-1082-46f3-909a-d0eb612f94ca" />

**¿Qué es nginx**
# COMPLETAR 

Descargar la imagen  **nginx** en la versión **alpine**
# COMPLETAR
Nginx (pronunciado "engine-x") es un servidor web muy popular y ligero, que también puede funcionar como:

Proxy inverso

Balanceador de carga

Servidor de caché

Servidor de aplicaciones estáticas (HTML, CSS, JS, etc.)

Es muy usado por su alto rendimiento, bajo consumo de recursos y facilidad de configuración.
### Listar imágenes

```
docker images
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
# COMPLETAR
<img width="799" height="858" alt="imagen" src="https://github.com/user-attachments/assets/5c4d0bd2-7855-4386-a4b9-5ed086ef9fba" />

**¿Con qué algoritmo se está generando el ID de la imagen**
# COMPLETAR
SHA.256
### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.S

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
# COMPLETAR
<img width="654" height="104" alt="imagen" src="https://github.com/user-attachments/assets/2d0642c2-7dfa-431d-a39f-56de8d05ed5f" />

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```
<img width="655" height="613" alt="imagen" src="https://github.com/user-attachments/assets/c671fa6f-3b29-4574-9f52-b50aa8b0ad9e" />
