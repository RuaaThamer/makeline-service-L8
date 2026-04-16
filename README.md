# Best Buy – Makeline Service

This is the Makeline Service for the **Best Buy Cloud-Native Final Project**.

The Makeline Service is a backend worker service responsible for processing customer
orders asynchronously. It consumes order messages from a message queue, processes them,
and persists completed orders to a database.

The service is implemented in **Go (Golang)** using the **Gin** framework and is part of a
microservices-based architecture deployed on **Azure Kubernetes Service (AKS)**.

This project is adapted from the **Algonquin Pet Store (On Steroids)** reference architecture
and rebranded for the Best Buy final project in CST8915.

---

## Architecture Context

The Makeline Service interacts with:
- **Order Service** – receives order messages via a message queue
- **Message Queue (RabbitMQ / Azure Service Bus)** – asynchronous communication
- **Database (MongoDB / Azure Cosmos DB)** – stores processed orders
- **Store Admin** – allows employees to view order status

Messaging is implemented using the **AMQP 1.0** protocol.

---

## Running the Service Locally (Optional)

> ⚠️ Local execution is for development and testing only.  
> In production, this service runs inside Kubernetes (AKS).

### Prerequisites
- Go (Golang)
- Docker
- Docker Compose

### Local Development

The Makeline Service relies on a message queue and a database.
A Docker Compose file is provided to simplify local testing.

```bash
docker compose up -d