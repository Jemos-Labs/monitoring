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

## Estructura del proyecto:
```
monitoring/
├── docker-compose.yaml     # Definición del stack
├── prometheus.yaml         # Configuración de Prometheus (jobs/targets)
├── README.md               # Documentación
└── docs/
    └── stack_diagram.png   # Diagrama del stack (opcional)
```

## Cómo usar:
Clona el repositorio:
   ```bash
   git clone git@github.com:Jemos-Labs/monitoring.git
   cd monitoring
   docker compose up -d
   ```

## Configurar Grafana
En el dashboard de Grafana

> Connections > Add new connection

> Buscar Prometheus y seleccionar

> Add new data source

> En connection: `http://prometheus:9090` y click en **save**

Para importar los dashboard en Grafana:

> Ve a **new > import**

> Seleccionar el ID correspondiente:

* 11074 → Node Exporter for Prometheus (monitor de servidor/Linux).

* 15172 → Docker & cAdvisor Dashboard. Monitorear contenedores Docker usando cAdvisor

* 8919 → Prometheus 2.0 Overview.

> Selecciona la datasource `Prometheus`

En `https://grafana.com/grafana/dashboards/` se encuentran los ID's para los diferentes dashboards.

> Click en **Load**

> En **VictoriaMetrics** selecciona **Prometheus**

> Finalmente, click en **Import**





