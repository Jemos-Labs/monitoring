# Monitoring
Este proyecto despliega un stack de monitoreo basado en **Prometheus**, **Grafana**, **Node Exporter**, **cAdvisor** y **Redis** usando Docker Compose.

## Apps o Servicios:

Node Exporter → métricas del host

cAdvisor → métricas de contenedores

Prometheus → recopila y almacena métricas de Node Exporter, cAdvisor y otros

Grafana → visualiza esas métricas con dashboards

Redis → soporte adicional (cache / almacenamiento temporal)


## Puertos expuestos:

- cadvisor: `localhost:8080`

- Grafana: `localhost:3100`

- Prometheus: `localhost:9090`

- Node Exporter → `http://localhost:9100` (solo dentro de la red Docker)

- Redis → Puerto `6379` (no expuesto al host, solo en red interna)

## Cómo usar:
1. Clona el repositorio:
   ```bash
   git clone https://github.com/tuusuario/tu-repo.git
   cd tu-repo 
   ```
