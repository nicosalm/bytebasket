# ByteBasket

A distributed data pipeline demonstrating real-time processing and analytics of e-commerce events using modern big data technologies.

```mermaid
flowchart LR
    subgraph Sources
        Web["Website Events"]
        App["Mobile App Events"]
        Cart["Shopping Cart Events"]
        Orders["Order Processing"]
    end

    subgraph Kafka["Apache Kafka"]
        Stream1["User Activity Stream"]
        Stream2["Transaction Stream"]
    end

    subgraph Processing
        RT["Real-time Processing"]
        Batch["Batch Processing"]
        ML["ML Pipeline"]
    end

    subgraph Storage
        Cassandra["Cassandra"]
        HDFS["HDFS"]
    end

    Web --> Stream1
    App --> Stream1
    Cart --> Stream1
    Orders --> Stream2

    Stream1 --> RT
    Stream2 --> RT
    Stream1 --> Batch
    Stream2 --> Batch

    RT --> Cassandra
    Batch --> HDFS
    HDFS --> ML
    ML --> Cassandra

    subgraph Analytics
        direction TB
        A["Real-time Dashboards"]
        B["Recommendation Engine"]
        C["Fraud Detection"]
        D["Analytics"]
    end

    Cassandra --> Analytics
```

## Tech Stack
- Apache Kafka: Event streaming and message queuing
- Apache Spark: Distributed data processing
- Apache Cassandra: NoSQL database for real-time queries
- HDFS: Distributed storage for large datasets
- Python: Primary implementation language

## System Components

### Event Producers
- User activity tracking
- Shopping cart events
- Transaction processing
- Mock data generation for testing

### Data Processing
- Real-time stream processing with Spark Streaming
- Basic ML pipeline for recommendations
- Fraud detection system
- Analytics computations

### Storage Layer
- Cassandra tables optimized for real-time queries
- HDFS structure for efficient data access
- Data retention policies

### Analytics
- Real-time metrics dashboard
- Historical trend analysis
- Product recommendations
- Transaction monitoring

## Project Structure
```
bytebasket/
├── README.md
├── docker-compose.yml
├── requirements.txt
├── config/
│   ├── kafka.yml
│   ├── spark.yml
│   └── cassandra.yml
├── src/
│   ├── producers/
│   │   ├── __init__.py
│   │   ├── user_events.py
│   │   ├── cart_events.py
│   │   └── transaction_events.py
│   ├── processors/
│   │   ├── __init__.py
│   │   ├── stream_processor.py
│   │   ├── fraud_detector.py
│   │   └── recommender.py
│   ├── storage/
│   │   ├── __init__.py
│   │   ├── cassandra_client.py
│   │   └── hdfs_client.py
│   └── analytics/
│       ├── __init__.py
│       └── metrics.py
├── tests/
│   ├── test_producers.py
│   ├── test_processors.py
│   └── test_storage.py
└── notebooks/
    └── analysis.ipynb
```

## Setup
[TODO]

## Development Status
Proof-of-concept project demonstrating distributed systems architecture.
