# MI APRENDIZAJE — Práctica con Docker

Al principio no tenía muy claro todo lo que se puede hacer con contenedores. Con la práctica quedó evidente: sirven para ejecutar servidores web y herramientas de CI/CD sin hacer magia. Aprendí a manejar imágenes, crear contenedores y a depurarlos cuando se portan mal.

---

## Comandos clave
```bash
# Descargar imágenes desde Docker Hub
docker pull <imagen:tag>

# Ver las imágenes disponibles localmente
docker images

# Eliminar una imagen
docker rmi <imagen:tag>

# Crear/ejecutar un contenedor (primer plano)
docker run --rm -it <imagen:tag> <comando>

# Ejecutar en segundo plano (detached)
docker run -d --name <nombre_contenedor> <imagen:tag>

# Ver logs de un contenedor
docker logs <contenedor>

# Ejecutar un comando dentro de un contenedor en ejecución
docker exec -it <contenedor> bash

# Inspeccionar detalles del contenedor (config, red, volúmenes...)
docker inspect <contenedor>
```
---
# Qué hice y aprendí

- Entendí para qué sirven los contenedores: desplegar servidores y pipelines sin liarla en el equipo local.

- Aprendí a descargar y listar imágenes, y a eliminarlas cuando sobran.

- Pude crear contenedores y distinguir cuándo correrlos en primer plano o con -d.

- Practiqué logs, exec e inspect para ver qué pasa cuando algo falla.

Para finalizar, lo que más me costó fue memorizar todos los comandos y entender que escribirlos correctamente es clave, porque un error mínimo puede hacer que la imagen no se reconozca.
Otro detalle importante que aprendí es que siempre hay que tener abierta la aplicación de Docker; al inicio me aparecían errores por eso, y se solucionaron simplemente al abrirla.

