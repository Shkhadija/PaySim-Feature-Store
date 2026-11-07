# PaySim Feature Store

A local ML Feature Store built with **Feast** and the **PaySim dataset**.

## Project Overview

This project demonstrates how to build and query a Feature Store for machine learning training and serving.

## Key Features

- Feature engineering from transaction data
- Point-in-Time historical feature retrieval
- Offline Store using Parquet
- Online Store using SQLite
- Feature materialization
- Online feature retrieval
- Offline and online feature consistency validation

## Technologies

- Python
- Feast
- Pandas
- SQLite
- Parquet
- Jupyter Notebook

## Project Structure

```text
PaySim-Feature-Store/
│
├── PaySim_Feature_Store_Project.ipynb
├── README.md
├── NOTES.md
│
└── feature_repo/
    ├── feature_definitions.py
    ├── feature_store.yaml
    ├── test_workflow.py
    └── data/
        └── paysim_features.parquet
```

## Feature Store Architecture

- **Offline Store:** Parquet file containing historical transaction features.
- **Online Store:** SQLite database for retrieving materialized features.
- **Registry:** Stores Feature Store metadata.

## Implemented Workflow

1. Data preparation and feature engineering
2. Feature Store configuration
3. Point-in-Time retrieval
4. Feature materialization
5. Online feature retrieval
6. Offline and online consistency validation


## Objective

To understand and demonstrate how Feast manages historical and online features for machine learning workflows.
