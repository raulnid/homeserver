Aquí con simplemente hacer `docker-compose up -d` estará todo funcionando, teniendo en cuenta que deberás modificar las IPs del archivo `prometheus.yml`.

También se habrá de tener en cuenta que se necesitará el servicio de `node-exporter` para que prometheus extraiga las métricas, en el equipo del `docker-compose` se ejecuta en conjunto con lo demás, sin embargo, en los equipos externos se deberá también usar:
```
docker run -d \
  --name=node_exporter \
  -p 9100:9100 \
  prom/node-exporter
  ```
Y añadir sus IPs en la configuración de `prometheus.yml`.
