# Un comando despliega Minecraft con Monitor usando Grafana

Requerimientos:
    - Si ya tienes una copia de seguridad, solo asegurate de restaurar el volumen o hacer un volumen bind en el docker-compose.

```shell
docker-compose up -d
```

Utiliza `docker-compose logs -f` para ver los registros de los contenedores. Cuando el servidor de Minecraft con el nombre de servicio `mc` esté activo y en funcionamiento, continúa con el siguiente paso.

## Acceso a Grafana

Abre un navegador en <http://localhost:3000> e inicia sesión inicialmente con el nombre de usuario **"admin"** y la contraseña **"admin"**. A continuación, se te pedirá que crees una nueva contraseña para el usuario admin.

Se ha configurado un panel llamado "MC Monitor" que se puede acceder en [la sección de paneles](http://localhost:3000/d/PpzSgJAnk/mc-monitor?orgId=1) en Grafana. Este panel utiliza la fuente de datos Prometheus que se ha configurado y se puede acceder en [la sección de fuentes de datos](http://localhost:3000/datasources).

## Ejecutar comando

Utiliza `docker exec mc mc-send-to-console` para ejecutar un comando, por ejemplo:

```shell
docker exec mc mc-send-to-console /time set day
```
