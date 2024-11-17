# Apache Server ITI Project

This project demonstrates the deployment and configuration of an Apache HTTP Server environment, created as part of the **ITI program**. It focuses on building a secure, scalable, and efficient web server solution with best practices in mind.

---

## **Purpose**

- Learn and practice Apache HTTP Server configuration and management.
- Deploy a web server with virtual hosting capabilities.
- Implement SSL/TLS encryption for secure communication.
- Gain hands-on experience with Linux server administration.

---

## **Features**

### 1. **Virtual Hosting**
- Host multiple websites on a single Apache server.
- Custom configurations for each virtual host.
- Organized file structure for easier management.

### 2. **SSL/TLS Implementation**
- Secure the server using self-signed or CA-signed SSL certificates.
- Enable HTTPS for encrypted communication.

### 3. **Server Optimization**
- Configuration for enhanced performance and scalability.
- Compression and caching mechanisms to improve response time.

### 4. **Logging and Monitoring**
- Set up access and error logs.
- Enable monitoring for troubleshooting and analytics.

### 5. **Automation**
- Scripts to automate the setup and deployment process.

---

## **System Requirements**

- **Operating System**: Linux-based OS (tested on Ubuntu/CentOS).
- **Software**:
  - Apache HTTP Server (`apache2` or `httpd`)
  - OpenSSL for SSL/TLS certificates
  - Bash shell for script execution
- **Hardware**: At least 1 GB RAM and 10 GB disk space.

---

## **Getting Started**

### Installation Steps

1. **Clone the repository**:
   ```bash
   git clone https://github.com/BaherFawzy/Apache-Server-ITI.git
   cd Apache-Server-ITI
   ```

2. **Run the setup script**:
   ```bash
   ./setup.sh
   ```
   - The script configures Apache, enables necessary modules, and sets up virtual hosts.

3. **Start the Apache server**:
   ```bash
   sudo systemctl start apache2   # For Ubuntu
   sudo systemctl start httpd     # For CentOS
   ```

4. **Test the server**:
   - Access your server using its IP or domain in a web browser.

---

## **Project Structure**

```plaintext
.
├── conf/                     # Apache configuration files
│   ├── apache2.conf          # Main Apache configuration
│   ├── ssl.conf              # SSL/TLS configuration
│   └── virtual-hosts.conf    # Virtual hosts configuration
├── public_html/              # Default web content directory
├── certs/                    # SSL/TLS certificates (self-signed or CA-signed)
├── logs/                     # Access and error logs
├── scripts/                  # Automation scripts for setup and maintenance
├── setup.sh                  # Main setup script
└── README.md                 # Documentation
```

---

## **Configuration Details**

### Virtual Hosts
- **File**: `conf/virtual-hosts.conf`
- Define separate virtual hosts for each domain/subdomain.
- Example:
  ```apache
  <VirtualHost *:80>
      ServerName example.com
      DocumentRoot /var/www/example.com
      ErrorLog /var/log/apache2/example.com-error.log
      CustomLog /var/log/apache2/example.com-access.log combined
  </VirtualHost>
  ```

### SSL/TLS Setup
- **File**: `conf/ssl.conf`
- Add paths to your SSL certificate and private key:
  ```apache
  SSLCertificateFile /path/to/certificate.crt
  SSLCertificateKeyFile /path/to/private.key
  ```

### Logging
- Access logs: `logs/access.log`
- Error logs: `logs/error.log`

---

## **Usage**

- **Start/Stop Apache**:
  ```bash
  sudo systemctl start apache2    # Start
  sudo systemctl stop apache2     # Stop
  sudo systemctl restart apache2  # Restart
  ```

- **Check Configuration**:
  ```bash
  apachectl configtest
  ```
