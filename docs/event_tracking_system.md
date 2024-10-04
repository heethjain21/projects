## Event Tracking System

Designed and built a robust system architecture and adherence to best practices in software development, ensuring scalability, security, and maintainability. 

### System Architecture
![event-tracking-system](https://github.com/user-attachments/assets/49ab2c3c-a1e5-4323-938b-c2d3d271f282)

### Key Decisions
Below are some of the key architectural decisions and practices that have been implemented: 

1. API-Based Cron for Scalability 
    - To avoid the pitfalls of traditional cron jobs in a horizontally scaled environment, this project utilises an API-based cron system. 
    - This approach ensures that scheduled tasks are executed once, regardless of the number of server instances running, thereby preventing duplication and ensuring efficiency. 

2. Dual Primary Keys in Database Design
    - The database schema employs two types of primary keys: an integer-based private key and a UID based public key. 
    - This design choice offers the following benefits
      - Space Efficiency: The integer-based private key consumes less space when used as a foreign key in related tables.
      - Security and Privacy: The UID-based public key prevents the exposure of the total number of rows in a table, enhancing privacy and security. 

3. Soft Deletes for Data Retention
    - The project adopts a soft-delete strategy for data management.
    - Instead of permanently removing records from the database, items are marked as deleted.
    - This approach allows for data recovery if needed and ensures compliance with legal and regulatory requirements.

4. Database Cleanup and Maintenance
    - The project includes automated routines for database cleanup and maintenance, ensuring optimal performance and data integrity and also GDPR compliance.

5. Decoupled services
    - The project architecture promotes decoupling of services, enhancing modularity and ease of maintenance. - This is implemented both inside the backend server as modules and in the entire system. 

### Security Measures

- OWASP Top 10: The project adheres to the OWASP Top 10 security standards, addressing common vulnerabilities and threats.
- Keys Rotation: Regular rotation of keys along with expiry, and auth keys minimizes the risk of unauthorised access.
- Least Privilege Access: Access control is strictly managed, ensuring that users and services have only the permissions necessary to perform their tasks. 

The entire project was deployed to AWS cloud infrastructure while ensuring automated deployments like CI/CD pipelines, automatic lint checks and automatic integration tests.

### Tech Stack

- PlanetScale (MySQL) 
- Redis
- Typescript
- Node.js (Express.js)
- AWS SQS
- AWS Lambda
- AWS Cloudwatch
- AWS X-Ray
- AWS App Runner
- AWS Event Bridge
- Github Actions
- Docker
