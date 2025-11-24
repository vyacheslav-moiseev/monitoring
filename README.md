### Проверка работы Blackbox Exporter

```bash
 curl "http://localhost:9115/probe?target=https://leads.su&module=http_2xx" |grep success

### Prometheus
![img.png](img.png)

### Grafana

![img_1.png](img_1.png)