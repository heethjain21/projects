## Blockchain Monitoring System

Designed and built a robust system architecture and adherence to best practices in software development, ensuring scalability, security, and maintainability.

The system tracks Blockchain events, and alerts clients based on the rules they setup. This system was built in a team effort with 3 engineers.

### System Architecture

![blockchain monitor-alert](https://github.com/user-attachments/assets/6d5f6eac-921d-4e9c-b70f-0b34bb6a138a)

I worked on the ETL pipeline along with setting up Clickhouse and checking and running rules to alert clients on Telegram (using Telegram Bot).

### Key Technical Decisions
Below are some of the key architectural decisions and practices that have been implemented:

1. Kafka-Clickhouse Connect - ETL
    - Kafka Engine Table in Clickhouse can work with Kafka fine, but it is a poll based solution, which means we have to constantly poll Kafka for events. It also requires an additional Table for Materialized Views which increases the database size.
    - Hence, Kafka-Clickhouse Connect was implemented to avoid redundant data + also ensuring push based system.

2. API-Based Cron for Scalability
    - To avoid the pitfalls of traditional cron jobs in a horizontally scaled environment, this project utilizes an API-based cron system.
    - This approach ensures that scheduled tasks are executed once, regardless of the number of server instances running, thereby preventing duplication and ensuring efficiency.

3. Soft Deletes for Data Retention
    - The project adopts a soft-delete strategy for data management.
    - Instead of permanently removing records from the database, items are marked as deleted.
    - This approach allows for data recovery if needed and ensures compliance with legal and regulatory requirements.

4. Decoupled services
    - The project architecture promotes decoupling of services, enhancing modularity and ease of maintenance.
    - This is implemented both inside the backend server as modules and in the entire system.

The entire project was deployed to AWS cloud infrastructure while ensuring best practices like automated deployments like CI/CD pipelines, automatic lint checks and automatic integration tests using jest.

### Tech Stack

- PostgreSQL
- Kafka
- Redis
- Clickhouse
- Typescript
- Node.js
- Docker
- Prometheus
- Terraform
- AWS ECS
- AWS Lambda
- AWS RDS
- AWS Cloudwatch
- AWS Event Bridge
