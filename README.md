# TFG - MONITOR DE NEUTRONES
## ESTACION BASE

### DESCRIPCIÓN
Este repositorio contiene la configuración necesaria para desplegar la estación base haciendo uso de contenedores docker

### REQUISITOS
- RAM 1GiB (2GiB recomendado)
- Docker engine
- Docker compose

### CONFIGURACION
Se debe generar un archivo **.env** que contenga la configuración de las variables de entorno de influxDB desclaradas en el archivo docker-compose  
Se debe incluir el token de influxDB en el archivo de configuración de Telegraf para una correcta conexión.

### EJECUCIÓN
Una vez realizadas las configuraciones oportunas, se debe lanzar el compose con el siguiente comando:
> docker compose up -d  

### ACCIONES POSTERIORES
- Comprobación de que los contenedores se han lanzado sin errores. Se pueden ver los logs con el comando:
  > docker compose logs
- Configurar Grafana para conectar a la base de datos influxDB.  
  Acceder a Grafana a través de la dirección:
  > http://ip_maquinia:3000  
  
  Las credenciales iniciales son:
  > **usuario**: admin  
  **contraseña**: admin
  
  Solicitará la creación de una nueva contraseña.  
  Se generará la conexión a influxDB usando los siguientes datos:
  > **QUERY LANGUAGE**: Flux  
    **URL**: http://influxDB:8086  
    **Auth**: Deseleccionar cualquier opción
    **Organization**: La configurada en influxDB
    **Token**: El configurado en el resto de servicios  

  Una vez añadidos todos los datos, pulsar en **Save and test**, si todo es correcto, encontrará los buckets de influxDB

- Configurar un nuevo Dashboard al gusto.


