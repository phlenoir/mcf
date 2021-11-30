# grafana+loki+promtail docker composition

## Launch the services

Use ```docker-compose up``` to launch the complete stack. Docker logs will be displayed in your terminal.

Use ```docker-compose up -d``` to launch the complete stack in the background. Then use ```docker logs <container_name>``` command to view latest logs from inidividual container, e.g. ```docker logs GRAFANA-DOCKER```

Use ```docker-compose up -d <service_name>``` to launch an individual service, e.g. ```docker compose -d grafana```. Beware of depends_on parameter.

## IIS logs 

See ```promtail/loki-promtail-conf.yml```. You may have to adapt the regex expressions to match your log format.