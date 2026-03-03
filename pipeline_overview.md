# Talabat – Data Engineering Pipeline
**Author:** Somaia Mahmoud Shapaan

## Introduction
Talabat operates as a leading food delivery and quick-commerce platform across MENA.
With millions of daily transactions, robust data engineering powers real-time operations,
analytics, and machine learning capabilities.

---

## 1. Data Sources
| Source | Description |
|--------|-------------|
| Mobile/Web events | User interactions, searches, sessions |
| Orders database | Customer details, items, pricing, locations, order status |
| Restaurant APIs | Menus, availability, pricing updates |
| Payment gateway logs | Transaction records, success/failure indicators |
| Rider GPS tracking | Location coordinates, speed, routes |
| Customer support | Ratings, complaints, chat logs |

---

## 2. Storage Architecture

### Data Lake (Raw Layer)
Raw, unprocessed data from all sources stored in distributed file systems.

### Staging Layer (Processed Data)
Cleaned and validated datasets with standardised formats, deduplicated records,
and handled missing values.

### Data Warehouse (OLAP)
Aggregated, structured data optimised for OLAP queries, supporting BI and reporting.

### Operational Databases (OLTP)
Transaction systems managing live orders, user accounts, payment processing, and inventory.

---

## 3. Processing Layer

### Stream Processing (Real-Time)
- GPS data processing for dynamic delivery-time estimation
- Order status updates (preparation → transit → delivery)
- Payment verification
- Restaurant availability monitoring

### Batch Processing
- Daily and weekly sales aggregations
- Data quality checks and cleansing operations
- Performance metrics (restaurant rankings, demand hotspots)
- Machine learning model training pipelines

---

## 4. Serving Layer

### Dashboards
Real-time overview of order activities: number of orders, status, delivery times,
and overall performance metrics.

### Machine Learning Applications
- Delivery time prediction models
- Personalised restaurant recommendation engines
- Fraudulent transaction detection systems

---

## 5. Pipeline Visualisation

```
[Data Sources] → [Ingestion]  → [Storage]   → [Processing]  → [Serving]
      ↓               ↓              ↓               ↓              ↓
 App Events      Kafka/API       Data Lake      Spark/Flink    Dashboards
 GPS Feeds    →  Streams   →    Staging    →   Batch Jobs  →  ML Models
 Orders DB       Connectors     Warehouse       Real-Time      APIs
 Payments                       OLTP DBs        Streaming
```

---

## References
- Delivery Hero SE. (2024). *Technology & Engineering Blog*. https://tech.deliveryhero.com
- Apache Software Foundation. (2024). *Apache Kafka Documentation*. https://kafka.apache.org/documentation/
- Databricks. (2024). *Lakehouse Architecture Guide*. https://www.databricks.com/glossary/data-lakehouse
- Kleppmann, M. (2017). *Designing Data-Intensive Applications*. O'Reilly Media.
- Narkhede, N., Shapira, G., & Palino, T. (2017). *Kafka: The Definitive Guide*. O'Reilly Media.
