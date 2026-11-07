# Project Notes

## 1. Dataset

The project uses the PaySim synthetic financial transaction dataset.

The original dataset contains 6,362,620 transaction records.

## 2. Feature Engineering

Three customer-level features were created:

| Feature | Description |
|---|---|
| `transaction_count` | Number of previous transactions |
| `total_amount` | Cumulative amount of previous transactions |
| `avg_amount` | Average amount of previous transactions |

The current transaction is excluded from these historical features.

## 3. Feature Store Configuration

- Feast version: 0.67.0
- Provider: Local
- Offline source: Parquet
- Online Store: SQLite
- Registry: SQLite

## 4. Point-in-Time Retrieval

A sample of 1,000 transactions was selected.

Feast retrieved historical features corresponding to each transaction timestamp, helping prevent future data leakage.

## 5. Materialization

A one-hour time interval was selected to demonstrate materialization without processing the entire dataset.

- Time interval: 2023-01-01 02:00–03:00
- Transactions: 552
- Unique customers: 552

Features from the selected interval were materialized from the Offline Store into the SQLite Online Store.

## 6. Online Feature Retrieval

A test customer was selected from the materialized data.

The customer's features were retrieved using Feast's `get_online_features()` method.

## 7. Offline Feature Retrieval

Historical features for the same customer and transaction timestamp were retrieved from the offline Parquet data.

## 8. Consistency Validation

Offline and online feature values were compared using Python `assert` statements.

The validation completed successfully:

```text
SUCCESS: Offline and Online features are consistent!
```

## 9. Important Notes

- The materialization step demonstrates a limited time interval rather than the entire dataset.
- The consistency check validates the selected customer's feature values.
- The SQLite Online Store and Feast Registry databases are generated locally during execution.
