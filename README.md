# vProfile Automated Provisioning (Windows/Mac/Intel) 🚀

## Introduction
This project is for DevOps automation, using Vagrant and shell scripts to automatically set up a multi-VM environment (CentOS/Ubuntu). It includes MySQL, Memcached, RabbitMQ, Tomcat, and Nginx servers.

---

## ⚙️ Workflow Overview

1. **Clone the repository** 📥
2. **Run `vagrant up`** 🏗️ — Vagrant provisions all VMs automatically.
3. **Provisioning scripts** 📝 (in `/scripts`) install and configure all required services on each VM:
   - Database (MySQL/MariaDB)
   - Memcached
   - RabbitMQ
   - Tomcat (with vProfile app)
   - Nginx (reverse proxy)
4. **Access the application** 🌐 via Nginx at [http://192.168.56.11](http://192.168.56.11)

> **Everything is automated!** Just one command and your full stack is ready for DevOps practice.

---

## 🗂️ File Structure

```
📦 Automated_provisioning_WinMacIntel
├── 📁 .git/                # Git version control
├── 📁 .vagrant/            # Vagrant state and metadata
├── 📁 scripts/             # All provisioning shell scripts
│   ├── backend.sh
│   ├── memcache.sh
│   ├── mysql.sh
│   ├── nginx.sh
│   ├── rabbitmq.sh
│   ├── tomcat.sh
│   └── tomcat_ubuntu.sh
├── 📄 Vagrantfile          # Vagrant multi-VM configuration
├── 📄 application.properties # App configuration (DB, cache, MQ, etc.)
└── 📄 README.md            # Project documentation
```

---

## 🖥️ Virtual Machine Structure
- **db01**: CentOS, MySQL/MariaDB database 🗄️
- **mc01**: CentOS, Memcached ⚡
- **rmq01**: CentOS, RabbitMQ 🐇
- **app01**: CentOS, Tomcat + Java + Maven + vProfile App ☕
- **web01**: Ubuntu, Nginx 🌐

---

## 📜 Main Scripts
- `Vagrantfile`: Defines all VMs and calls provisioning scripts.
- `scripts/mysql.sh`: Installs MariaDB/MySQL, creates DB, and sets up user permissions.
- `scripts/memcache.sh`: Installs and configures Memcached.
- `scripts/rabbitmq.sh`: Installs and configures RabbitMQ.
- `scripts/tomcat.sh`: Installs Tomcat, Java, Maven, builds and deploys the vProfile app.
- `scripts/nginx.sh`: Installs Nginx and sets up reverse proxy.
- `application.properties`: Application configuration for DB, Memcached, RabbitMQ, Elasticsearch, etc.

---

## 🚀 Installation & Usage

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
   - Open your browser and go to: [http://192.168.56.11](http://192.168.56.11)

---

## 🛠️ Configuration Details
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

---

## 📑 Script Summaries
- **mysql.sh**: Installs MariaDB, creates DB and user, and imports the dump file.
- **memcache.sh**: Installs Memcached and sets up firewall rules.
- **rabbitmq.sh**: Installs RabbitMQ, creates user, and sets permissions.
- **tomcat.sh**: Installs Java, Maven, Tomcat, clones and deploys the vProfile app.
- **nginx.sh**: Installs Nginx and sets up reverse proxy for Tomcat.

---

## 📝 Notes
- All scripts are automated; no manual steps are required.
- Internet connection is required during VM provisioning.
- For advanced application settings, see `application.properties`.

---

**This project is very useful for DevOps practice, especially for learning multi-tier architecture and automation.** 🚦 