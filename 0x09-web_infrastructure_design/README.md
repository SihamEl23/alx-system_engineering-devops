# 0x09. Web Infrastructure Design

## Project Overview for Task 0 :

In Task 0, we designed a basic web infrastructure for hosting the website reachable via www.foobar.com. The infrastructure consists of a single server with a LAMP stack, incorporating components like a web server (Nginx), an application server, application files, a MySQL database, and a domain name (foobar.com) configured with a www record pointing to our server's IP (8.8.8.8).

## Understanding the Infrastructure:

- **Server**: A server is a computer system that responds to requests from users and serves web content.
- **Domain Name**: The domain name (foobar.com) is a human-readable address for accessing websites and is configured to map to our server's IP.
- **DNS Record**: The "www" in www.foobar.com is a DNS record known as a CNAME that points to our server's IP address.
- **Web Server (Nginx)**: It handles HTTP requests from users and serves static content, like HTML, CSS, and images.
- **Application Server**: Responsible for processing dynamic content, executing code, and managing business logic.
- **Database (MySQL)**: Stores and manages data needed for the website's operation.
- **Communication**: The server communicates with users' computers through HTTP, serving web pages and dynamic content.

## Issues with the Infrastructure:

1. **Single Point of Failure (SPOF)**: The infrastructure relies on a single server, making it vulnerable to disruptions if the server fails.
2. **Downtime during Maintenance**: Updates or maintenance on the web server may lead to downtime as it requires restarting, affecting website availability.
3. **Scaling Challenges**: Scaling to handle high incoming traffic is limited with a single server setup, potentially leading to performance issues during traffic spikes.

## ## Project Overview for Task 1 :
In Task 1, we designed a distributed web infrastructure for hosting www.foobar.com. This infrastructure utilizes multiple components, including two servers, a web server (Nginx), an application server, a load balancer (HAproxy), application files, and a MySQL database.

## Understanding the Infrastructure:

- **Web Server and Application Server**: These components are separated to improve scalability, maintainability, and security.
- **Load Balancer (HAproxy)**: Distributes incoming traffic across web and application servers, enhancing reliability and performance.
- **Load Balancer Algorithm**: HAproxy is configured with a load balancing algorithm (e.g., round-robin) to evenly distribute requests among the servers.
- **Active-Active Setup**: The load balancer enables an active-active setup where both servers handle requests simultaneously, ensuring redundancy and increased capacity.
- **Database Primary-Replica Cluster**: The database is configured as a primary-replica (master-slave) cluster, ensuring data redundancy and high availability.
- **Primary vs. Replica**: The primary node handles write operations, while replicas replicate data and handle read operations. The primary node is critical for data integrity, while replicas can scale read operations.

## Issues with the Infrastructure:

1. **Single Point of Failure (SPOF)**: Potential SPOF exists in the load balancer and the database server. If not addressed, failures in these components can disrupt service.
2. **Security Issues**: Lack of a firewall and HTTPS can expose the infrastructure to security vulnerabilities and data breaches.
3. **No Monitoring**: Without monitoring, issues and performance bottlenecks may go unnoticed, impacting the infrastructure's reliability.

## ## Project Overview for Task 2 :
In Task 2, we designed a secured and monitored web infrastructure for www.foobar.com. This infrastructure includes three firewalls, SSL certificate implementation for HTTPS, and monitoring clients (Sumo Logic) for data collection.

## Understanding the Infrastructure:

- **Firewalls**: Three firewalls are added for security. Inbound firewalls filter incoming connections, and outbound firewalls restrict server-initiated outbound connections, preventing unauthorized access and enhancing security.
- **SSL Certificate (HTTPS)**: HTTPS is implemented to encrypt and secure data in transit between users and the web server, ensuring data confidentiality and integrity.
- **Monitoring (Sumo Logic)**: Sumo Logic clients on each server collect performance and log data, enabling real-time insights, issue detection, and performance optimization.
- **Monitoring Data Collection**: Monitoring tools collect data related to server performance, such as response times, error rates, and more, for proactive issue detection and performance improvement.
- **Monitoring Web Server QPS**: To monitor web server Queries Per Second (QPS), configure the monitoring tool to count incoming requests per second. Alerts can be set to notify of QPS thresholds being exceeded.

## Issues with the Infrastructure:

1. **Terminating SSL at Load Balancer Level**: Terminating SSL at the load balancer can create SSL decryption bottlenecks and should be offloaded to specialized devices.
2. **Single MySQL Server for Writes**: The single MySQL server for writes is a potential SPOF. Implementing redundancy or a database cluster is essential for high availability.
3. **Uniform Server Components**: Having servers with identical components may limit flexibility and could result in all servers being affected by a single component issue. Diversifying components across servers enhances security and maintainability.
