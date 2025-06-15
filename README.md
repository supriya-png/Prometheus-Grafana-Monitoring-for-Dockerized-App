# Prometheus + Grafana Monitoring for Dockerized App

## Description

This project demonstrates how to monitor a Dockerized Python web application (Flask or FastAPI) using Prometheus and Grafana. Prometheus Node Exporter is used to collect host-level metrics, and Grafana is used to visualize them.

The entire monitoring stack is orchestrated using Docker Compose.

## Technologies Used

- Python (Flask or FastAPI)
- Prometheus
- Prometheus Node Exporter
- Grafana
- Docker
- Docker Compose

## Architecture

- Python web app runs in Docker container.
- Prometheus collects metrics from Node Exporter and (optionally) from the Python app itself.
- Grafana visualizes Prometheus data.
- Docker Compose manages all services together.

## Folder Structure

prometheus-grafana-monitoring/
├── app/
│ └── app.py
├── prometheus/
│ └── prometheus.yml
├── grafana/
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
└── README.md


## Setup Instructions

### Prerequisites

- Docker installed
- Docker Compose installed

### Build and Run

Clone the repository and navigate into the project directory.


docker-compose up --build
Access the Services
Web App: http://localhost:5000

Prometheus: http://localhost:9090

Grafana: http://localhost:3000

Grafana Login
Default credentials:

Username: admin

Password: admin

You can change the password after first login.

Add Prometheus as Data Source in Grafana
URL: http://prometheus:9090

Create Dashboards
Use built-in Grafana dashboards or import community dashboards.

Visualize CPU, memory, disk, network usage from Node Exporter.

Clean Up
To stop and remove all containers:

docker-compose down
Optional: Export Python App Metrics
Expose custom metrics using prometheus_client package.

Update prometheus.yml to scrape metrics from app.

Example Python code:

from prometheus_client import start_http_server, Counter

c = Counter('my_requests_total', 'Total HTTP Requests')
start_http_server(8000)

Author
Supriya S P
