# Data Engineering Pipeline – Talabat

**Author:** Somaia Mahmoud Shapaan

A conceptual report describing a real-time data engineering pipeline inspired by Talabat's
platform architecture, covering ingestion, storage layers, stream/batch processing, and the
serving layer.

## Files

| File | Description |
|------|-------------|
| `pipeline_overview.md` | Full pipeline documentation with architecture diagram |

## Pipeline Summary

```
[Data Sources] → [Ingestion] → [Storage] → [Processing] → [Serving]
```

| Stage | Technology Examples |
|-------|---------------------|
| Ingestion | Apache Kafka, REST APIs, Stream connectors |
| Storage | Data Lake, Staging, Data Warehouse (OLAP), OLTP |
| Processing | Apache Spark, Flink (batch + stream) |
| Serving | Dashboards, ML models, REST APIs |
