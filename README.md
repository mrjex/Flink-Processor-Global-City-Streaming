# Flink Processor

This Flink Processor component is an integrated submodule and Docker container of the [Global City Streaming](https://github.com/mrjex/Global-City-Streaming) project. It is designed to receive streaming data from the [Kafka Producer](https://github.com/mrjex/Kafka-Producer-Global-City-Streaming), process and aggregate the incoming information, and then insert the results into the [PostgresSQL Component](https://github.com/mrjex/Postgres-Global-City-Streaming) database for further analysis and storage.

## Data Aggregation

The Flink Processor performs real-time aggregation of incoming data samples using time windowing techniques. Specifically:

- **Samples:** The processor receives continuous streams of data samples, each representing a measurement or event from a city sensor or data source.
- **Time Windows:** Data is grouped into fixed-size time windows (e.g., every minute, hour, etc.), allowing for efficient batch processing and aggregation of events that occur within the same period.
- **Averages:** Within each time window, the processor calculates statistical aggregates using average temperature based on the collected samples

These aggregated results are then forwarded to the PostgresSQL database, where they can be queried and analyzed for trends
