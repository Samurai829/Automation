#-------------------------------------------------------------
# AUTOMATIZACION HERRAMIENTAS DE MONITORIZACION 
#-------------------------------------------------------------

# CONSTRUCCION Y DESPLIEGUE DE MONITOR
NAME-1 = prometheus
NAME-2 = grafana
NAME-3 = redis
NAME-4 = redis-exporter

build_prometheus:
	@echo 'Construccion y ejecucion de $(NAME-1)'
	cd prometheus && docker-compose up -d
	docker ps --filter "status=running"

build_grafana:
	@echo 'Construccion y ejecucion de $(NAME-2)'
	cd grafana && docker-compose up -d
	docker ps --filter "status=running"

build_redis:
	@echo 'Construccion y ejecucion de $(NAME-3)'
	cd redis && docker-compose up -d
	docker ps --filter "status=running"

build_exporter:
	@echo 'Construccion y ejecucion de $(NAME-4)'
	cd redis-exporter && docker-compose up -d
	docker ps --filter "status=running"

# Ejecucion de todos servicios en un solo comando
build_monitor:
	@echo 'Levantamiento de todo MONITOR'
	$(MAKE) build_prometheus
	$(MAKE) build_grafana
	$(MAKE) build_redis
	$(MAKE) build_exporter
	docker ps --filter "status=running"
	docker stats



# Detencion los servicios de Monitor
stop_prometheus:
	@echo 'Detencion de ejecucion del servicio $(NAME-1)'
	cd prometheus && docker-compose stop $(NAME-1)

stop_grafana:
	@echo 'Detencion de ejecucion del servicio $(NAME-2)'
	cd grafana && docker-compose stop $(NAME-2)

stop_redis:
	@echo 'Detencion de ejecucion del servicio $(NAME-3)'
	cd redis && docker-compose stop $(NAME-3)

stop_exporter:
	@echo 'Detencion de ejecucion del servicio $(NAME-4)'
	cd prometheus && docker-compose stop $(NAME-4)

# Detencion de todos los servicios en un solo comando
stop_all:
	@echo 'Detencion de todos los servicios MONITOR'
	$(MAKE) stop_prometheus
	$(MAKE) stop_grafana
	$(MAKE) stop_redis
	$(MAKE) stop_exporter
	docker ps --filter "status=running"		
	@echo 'Todos los servicios de MONITOR fueron detenidos'



# Eliminacion de servicios en un solo comando
delete_prometheus:
	@echo 'Eliminacion de $(NAME-1)'
	cd prometheus && docker-compose down
	@echo 'Servicio eliminado'

delete_grafana:
	@echo 'Eliminacion de $(NAME-2)'
	cd grafana && docker-compose down
	@echo 'Servicio eliminado'

delete_redis:
	@echo 'Eliminacion de $(NAME-3)'
	cd redis && docker-compose down
	@echo 'Servicio eliminado'

delete_exporter:
	@echo 'Eliminacion de $(NAME-4)'
	cd redis-exporter && docker-compose down
	@echo 'Servicio eliminado'
	
# Eliminacion de todos servicios MONITOR en un solo comando
delete_monitor:
	@echo 'Eliminacion de todo MONITOR'
	$(MAKE) delete_exporter
	$(MAKE) delete_redis
	$(MAKE) delete_prometheus
	$(MAKE) delete_grafana
	@echo 'Todos los servicios MONITOR fueron eliminados'
