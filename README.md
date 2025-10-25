# airflow-server

Airflow server for ETL workflows. Uses [dag factory](https://www.astronomer.io/docs/learn/dag-factory) from Astronomer.

## Project structure
```
.
├── Dockerfile
├── LICENSE
├── README.md
├── airflow
├── dags
├── docker-compose.yml
├── include
│   ├── dags
│   └── sql
├── plugins
├── requirements.txt
├── src
└── tests
```
## Setting up a local environment

### Setting up a local environment with Docker
```bash
docker-compose build
```
```bash
docker-compose up -d
```

### Setting up local environment with Podman

1. Build the image from docket-compose.
```bash
podman build -t airflow-server .
```
2. Start the container.
```bash
podman-compose up -d
```

4. Launch the Airflow UI at http://localhost:8080 (login with airflow/airflow).


### Other useful commands

Stop the container:
```bash
podman-compose down
```

Read the scheduler logs:

```bash
cat logs/scheduler/2025-10-22/dag_factory_loader.py.log
```