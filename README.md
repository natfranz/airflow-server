# airflow-server

```
airflow-server/
├── .env                          # Environment variables (not in git)
├── .gitignore
├── README.md
├── docker-compose.yml            # Docker orchestration
├── Dockerfile                    # Custom Airflow image
├── requirements.txt              # Python dependencies
│
├── airflow/
│   └── airflow.cfg              # Airflow configuration
│
├── dags/                        # DAG definitions only
│   ├── __init__.py
│   ├── etl_pipeline_python.py   # DAG using Python transformations
│   ├── etl_pipeline_sql.py      # DAG using SQL transformations
│   └── etl_pipeline_dbt.py      # DAG with dbt (future)
│
├── include/                     # Supporting files for DAGs
│   ├── sql/                     # SQL transformation scripts
│   │   ├── extract/
│   │   │   └── source_queries.sql
│   │   ├── transform/
│   │   │   ├── transform_step1.sql
│   │   │   └── transform_step2.sql
│   │   └── load/
│   │       └── destination_queries.sql
│   │
│   └── config/                  # Configuration files
│       ├── connections.yaml     # Airflow connections config
│       └── variables.yaml       # Airflow variables config
│
├── src/                         # Python transformation logic
│   ├── __init__.py
│   ├── extractors/              # Data extraction modules
│   │   ├── __init__.py
│   │   ├── api_extractor.py
│   │   └── database_extractor.py
│   │
│   ├── transformers/            # Data transformation modules
│   │   ├── __init__.py
│   │   ├── base_transformer.py
│   │   ├── data_cleaner.py
│   │   └── data_aggregator.py
│   │
│   ├── loaders/                 # Data loading modules
│   │   ├── __init__.py
│   │   ├── database_loader.py
│   │   └── file_loader.py
│   │
│   └── utils/                   # Shared utilities
│       ├── __init__.py
│       ├── db_helpers.py
│       ├── logger.py
│       └── validators.py
│
├── plugins/                     # Custom Airflow plugins
│   ├── __init__.py
│   ├── operators/               # Custom operators
│   │   ├── __init__.py
│   │   └── custom_sql_operator.py
│   │
│   └── hooks/                   # Custom hooks
│       ├── __init__.py
│       └── custom_db_hook.py
│
├── dbt/                         # dbt project (future integration)
│   └── analytics/
│       ├── dbt_project.yml
│       ├── profiles.yml
│       ├── models/
│       │   ├── staging/
│       │   └── marts/
│       ├── macros/
│       ├── tests/
│       └── seeds/
│
├── tests/                       # Test suite
│   ├── __init__.py
│   ├── unit/
│   │   ├── test_extractors.py
│   │   ├── test_transformers.py
│   │   └── test_loaders.py
│   ├── integration/
│   │   └── test_pipeline_e2e.py
│   └── fixtures/
│       └── sample_data.json
│
├── logs/                        # Airflow logs (gitignored)
│
└── data/                        # Local data storage (gitignored)
    ├── raw/
    ├── processed/
    └── output/

```