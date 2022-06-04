# MONITOR
## Que es Monitor?

Monitor es un conjunto de Aplicaciones las cuales tienen como objetivo la monitorizacion de usos 
de recursos y mas en el sistema, todo esto ha sido compilado en varios Docker Compose y luego he 
decidido correrlo en **Makefile** para asi automatizarlo con solo un comando el cual seria 
`Make build_monitor` en la consola de comandos de windows o terminal de linux.

NOTA: Es requerido tener instalado **Make** y **Docker** para poder usarlo sin problemas.
## Como usarlo?

### EJECUCION:
Es simple y sencillo de usar, lo unico es correr `Make build_monitor` para su ejecucion luego para 
visualizar los recursos tendrias que ir a la direccion `localhost:9090` para visualizar **PROMETHEUS** 
o `localhost:3000` para visualizar grafana.

NOTA: **GRAFANA** pide iniciar sesion con usuario y constraseña caso de no saber cuales son 
las **CREDENCIALES PREDETERMINADAS** son **admin** para usuario y contraseña.

### DETENCION:
Solo debes usar `stop_monitor` o indicar cual es el **Servicio (Contenedor)** que 
deseas detener de monitor.

### ELIMINACION:
Por igual solo debes usar `delete_monitor` o indicar cual es el **Servicio (Contenedor)** que 
deseas eliminar de monitor.

## INFORMACION IMPORTANTE

Esta SECCION puedes usarla para Monitorear, ademas si deseas puedes editar y mejorar su uso si 
deseas ya que es totalmente personalizable y facil de escalar.