# vProfile Automated Provisioning (Windows/Mac/Intel)

## Introduction
This project is for DevOps automation, using Vagrant and shell scripts to automatically set up a multi-VM environment (CentOS/Ubuntu). It includes MySQL, Memcached, RabbitMQ, Tomcat, and Nginx servers.

## Virtual Machine Structure
- **db01**: CentOS, MySQL/MariaDB database
- **mc01**: CentOS, Memcached
- **rmq01**: CentOS, RabbitMQ
- **app01**: CentOS, Tomcat + Java + Maven + vProfile App
- **web01**: Ubuntu, Nginx

## Main Scripts
- `Vagrantfile`: Defines all VMs and calls provisioning scripts.
- `mysql.sh`: Installs MariaDB/MySQL, creates DB, and sets up user permissions.
- `memcache.sh`: Installs and configures Memcached.
- `rabbitmq.sh`: Installs and configures RabbitMQ.
- `tomcat.sh`: Installs Tomcat, Java, Maven, builds and deploys the vProfile app.
- `nginx.sh`: Installs Nginx and sets up reverse proxy.
- `application.properties`: Application configuration for DB, Memcached, RabbitMQ, Elasticsearch, etc.

## Installation and Running Steps
1. **System Requirements:**
   - Windows/Mac/Linux (Intel)
   - Vagrant
   - VirtualBox

2. **Clone the Project:**
   ```sh
   git clone <insert your repository link here>
   cd Automated_provisioning_WinMacIntel
   ```

3. **Start Vagrant VMs:**
   ```sh
   vagrant up
   ```
   This command will automatically set up and provision all VMs.

4. **Access the Application:**
   - Open your browser and go to the Nginx (web01) VM IP: http://192.168.56.11

## Configuration Details
- **Database:**
  - Host: db01
  - User: admin
  - Password: admin123
- **Memcached:**
  - Active Host: mc01, Port: 11211
- **RabbitMQ:**
  - Host: rmq01, Port: 5672, User: test, Password: test
- **Tomcat App:**
  - Host: app01, Port: 8080
- **Nginx:**
  - Host: web01, Port: 80 (reverse proxy)

## Script Summaries
- **mysql.sh**: Installs MariaDB, creates DB and user, and imports the dump file.
- **memcache.sh**: Installs Memcached and sets up firewall rules.
- **rabbitmq.sh**: Installs RabbitMQ, creates user, and sets permissions.
- **tomcat.sh**: Installs Java, Maven, Tomcat, clones and deploys the vProfile app.
- **nginx.sh**: Installs Nginx and sets up reverse proxy for Tomcat.

## Notes
- All scripts are automated; no manual steps are required.
- Internet connection is required during VM provisioning.
- For advanced application settings, see `application.properties`.

---

**This project is very useful for DevOps practice, especially for learning multi-tier architecture and automation.** 