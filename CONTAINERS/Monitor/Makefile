#-------------------------------------------------------------
# AUTOMATIZACION HERRAMIENTAS DE MONITORIZACION 
#-------------------------------------------------------------

# CONSTRUCCION Y DESPLIEGUE DE MONITOR
NAME-1 = PROMETHEUS
NAME-2 = GRAFANA
NAME-3 = REDIS
NAME-4 = REDIS-EXPORTER

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

build_monitor:
	@echo 'Levantamiento de todo MONITOR'
	$(MAKE) build_prometheus
	$(MAKE) build_grafana
	$(MAKE) build_redis
	$(MAKE) build_exporter
	docker ps --filter "status=running"
	docker stats