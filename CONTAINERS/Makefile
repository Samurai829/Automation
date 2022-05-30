#---------------------------------------------------
# 1. CONTRUCCION DE UN CONTENEDOR MEDIANTE MAKEFILE
#---------------------------------------------------

#---------------------------------------------------
# Construimos un contenedor
# Asignamos un nombre al contenedor
# Asignamos un tag mediante variable
#---------------------------------------------------

# Variables
TAG = 3
CONTAINER_NAME = redis
IMAGE_NAME = redis


# Construcion de un CONTENEDOR con MAKEFILE

build_container:
	@echo 'Construcion del Contenedor $(CONTAINER_NAME) con el TAG:$(TAG)'
	docker pull $(IMAGE_NAME):$(TAG)
	@echo 'Ejecucion del Contenedor $(CONTAINER_NAME)'
	docker run -d --name $(CONTAINER_NAME) $(IMAGE_NAME):$(TAG)
	@echo 'Visualizacion del Contenedor $(CONTAINER_NAME)'
	docker ps -a --filter "name=$(CONTAINER_NAME)"