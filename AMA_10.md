# Interview Questions & Short Answers

## 1. Difference between Docker and Virtual Machine (VM)

| Docker | Virtual Machine |
|--------|-----------------|
| Uses the host OS kernel | Has its own guest OS |
| Lightweight | Heavyweight |
| Starts in seconds | Takes minutes to boot |
| Uses fewer resources | Uses more CPU/RAM |
| Best for deploying applications | Best for running multiple operating systems |

---

## 2. In which format does MongoDB store data?

MongoDB stores data in **BSON (Binary JSON)** format internally.

- Documents are represented like JSON.
- BSON supports additional data types such as Date, ObjectId, Binary, etc.

Example:
```json
{
  "_id": ObjectId("..."),
  "name": "Naman",
  "age": 23
}
```

---

## 3. In Redis Pub/Sub, what happens if the consumer is offline?

- The consumer **misses the message**.
- Redis Pub/Sub does **not** store messages.
- Messages are delivered only to subscribers that are online at the time of publishing.

---

## 4. CPU-bound vs I/O-bound Tasks

### CPU-bound
- Limited by CPU processing.
- Examples:
  - Image processing
  - Encryption
  - Mathematical computations

### I/O-bound
- Limited by waiting for external resources.
- Examples:
  - Database queries
  - File reading/writing
  - API calls
  - Network communication

---

## 5. What is the first principle of SOLID?

**S – Single Responsibility Principle (SRP)**

A class should have **only one reason to change**, meaning it should have only one responsibility.

Example:
- `Invoice` → calculate invoice.
- `InvoicePrinter` → print invoice.

---

## 6. Difference between ACK and NACK in RabbitMQ

### ACK (Acknowledgement)
- Consumer successfully processed the message.
- RabbitMQ removes the message from the queue.

### NACK (Negative Acknowledgement)
- Consumer failed to process the message.
- Message can be requeued or discarded based on configuration.

---

## 7. What is Pika?

**Pika** is a **Python client library** used to communicate with RabbitMQ.

It allows Python applications to:
- Publish messages
- Consume messages
- Create queues and exchanges

---

## 8. Difference between SQL and NoSQL

| SQL | NoSQL |
|------|--------|
| Relational database | Non-relational database |
| Fixed schema | Flexible schema |
| Stores data in tables | Stores documents, key-value, graph, or column data |
| Uses SQL queries | Different query mechanisms |
| Better for complex joins | Better for scalability and high throughput |

Examples:
- SQL: MySQL, PostgreSQL
- NoSQL: MongoDB, Redis, Cassandra

---

## 9. What is the purpose of partitions in Kafka?

Partitions provide:
- **Scalability** by splitting data across brokers.
- **Parallel processing** by allowing multiple consumers to read simultaneously.
- **High throughput** for faster message processing.
- **Ordering** of messages within each partition.

---

## 10. Why do we use Apache Kafka?

Apache Kafka is used for **real-time event streaming**.

Common use cases:
- High-throughput message processing
- Microservices communication
- Log aggregation
- Real-time analytics
- Event-driven architecture

### Benefits
- High performance
- Fault tolerant
- Scalable
- Durable message storage
- Supports multiple producers and consumers
