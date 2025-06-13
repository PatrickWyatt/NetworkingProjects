Here's a README file tailored for your GitHub portfolio, incorporating the project summaries and highlighting key skills and technologies:

---

## **Advanced Web Server & Infrastructure Management Labs**

This repository showcases a collection of hands-on projects demonstrating expertise in **Apache web server administration**, **Active Directory services**, and **security configurations** within virtualized environments. These labs focus on practical implementation of network, web, and security principles, ideal for portfolio presentation.

---

### **Project Details**

Each section below provides a summary of a distinct project, detailing its scope, the technologies involved, and the skills demonstrated.

#### **1. Apache Server Optimization & Scripting**

**Description:**
This project involved a comprehensive **optimization and configuration of an Apache web server** to enhance performance, monitor usage, and integrate dynamic content. Key steps included:
*   **Optimizing Apache server performance** by configuring the Multi-Process Module (MPM), specifically the `worker` module. This setup was tailored to handle up to **180 simultaneous client requests** efficiently, initiating with 12 httpd server processes, maintaining 6-12 idle processes, queuing up to 100 pending requests, enabling persistent connections with a 50-request limit and 20-second timeout, and setting a 55-second maximum request duration.
*   Implementing **Apache server monitoring** by enabling `ExtendedStatus` and configuring `server-status` and `server-info` handlers to be accessible only within the **192.168.50.0/24 subnet**.
*   Configuring the web server to use **Common Gateway Interface (CGI) bins**, demonstrated by creating and deploying a **Perl script** in the `/var/www/cgi-bin` directory to display specific text.
*   Setting up the web server for **PHP compatibility**, which included installing PHP and developing a PHP script that displayed "Hello my friend!" to users from the **192.168.100.0/24 subnet** and "Hello stranger!" to others, located in `/var/www/html_project3/q4`.
*   Integrating **MySQL with PHP**: installing MySQL, creating an "employees" table with `name` and `salary` fields in a "company" database, inserting records, and developing a PHP script to connect to this database and display its contents as an HTML table in the web browser. Permissions and SELinux configurations were adjusted to enable network connectivity for Apache.
*   Configuring the web server to use **SSL (Secure Sockets Layer)** by installing `mod_ssl`, generating a self-signed certificate, and enabling `SSLEngine` to secure access via HTTPS.

**Skills Demonstrated:**
*   **Apache Server Administration & Optimization** (MPM configuration, performance tuning).
*   **Web Server Monitoring** (Apache status handlers).
*   **CGI Scripting** (Perl).
*   **PHP Development** (dynamic content generation, IP-based conditional logic).
*   **Database Integration** (MySQL setup, table management, PHP-MySQL connectivity).
*   **SSL/TLS Configuration** (certificate generation, HTTPS enablement).
*   **Linux System Administration** (file permissions, SELinux, service management).
*   **Network Concepts** (subnets, IP addresses).

#### **2. Apache Web Server Installation and Advanced Security Configuration**

**Description:**
This project focused on the **installation and in-depth security configuration of an Apache web server**, demonstrating various authentication, accessibility, and authorization mechanisms. Key accomplishments included:
*   **Installing and configuring the Apache server** to serve web pages from `/var/www/html_project1`, including creating a homepage (`index.html`) utilizing various HTML tags and internal hyperlinks.
*   Implementing **user authentication via Directory directives** and `.htaccess` files for several "secure" directories (`secure1` through `secure7`), establishing diverse access policies:
    *   `secure1`: Restricted to `user01` with a specific password from any subnet.
    *   `secure2`: Restricted to `user01` only when connecting from the **192.168.50.0/24 subnet**.
    *   `secure3`: Accessible to `user01` **OR** any user from the **192.168.50.0/24 subnet**.
    *   `secure4`: Restricted to `user02` with a specific password.
    *   `secure5`: Restricted to `user01` via `.htaccess` from any subnet.
    *   `secure6`: Restricted to `user01` via `.htaccess` only from the **192.168.50.0/24 subnet**.
    *   `secure7`: Accessible to `user01` **OR** any user from the **192.168.50.0/24 subnet** via `.htaccess`.
*   Configuring **IP-based accessibility controls** for multiple project directories (`Project1` to `Project4`), including specific restrictions for various subnets (e.g., **10.35.16.0/24, 10.35.17.0/24, 192.168.100.0/24**) and blocking access to certain file types (e.g., `secret.*`, `*.gif`, `test.html`). A global directive was added to prevent access to all `*.txt` files across all directories.
*   Implementing **departmental authorization** using Apache aliases and fine-grained access rules based on network subnets and file types for "vendors", "accountants", "administrators", and "programmers" web directories (e.g., accountants cannot view `*.html` files, programmers cannot view `*.gif` or `*.jpg` files).

**Skills Demonstrated:**
*   **Apache Web Server Installation & Basic Configuration**.
*   **User Authentication & Authorization** (Basic Authentication, `.htaccess` files, `<Directory>` and `<Files>` directives).
*   **Access Control Lists (ACLs)** based on IP addresses and subnets.
*   **File Type Restrictions**.
*   **Apache Aliases**.
*   **HTML Basics**.
*   **Network Security Principles**.
*   **Linux Command Line Interface (CLI)** for system and server configuration.

#### **3. Managing a Certificate Authority Server in Active Directory**

**Description:**
This project involved the setup and management of a **Certificate Authority (CA) server within an Active Directory (AD) domain** to issue and manage various types of digital certificates, ensuring secure communication and authentication. Key achievements include:
*   **Issuing User Certificates** from an Enterprise CA, which involved ensuring users had email addresses assigned to their profiles in AD. A new certificate template named "**User-Auth**" was created, configured for a 1-year validity period, published in Active Directory, and permissions were set to allow Authenticated Users to enroll and autoenroll. Manual and automatic user certificate requests were performed and verified.
*   Enabling **Automatic Certificate Enrollment** in Active Directory through Group Policy Objects (GPO), streamlining the process of certificate issuance to users.
*   Issuing **Digitally Signed Documents and Files Certificates** from the Enterprise CA. This required duplicating the "User Signature Only" template, creating a "Digital Signature" template, and configuring it specifically for digital signature key usage. Permissions were also set for Authenticated Users to enroll and autoenroll. Certificate reception was manually verified on client machines.
*   **Securing Internal Web Servers with SSL/TLS Certificates**. This involved creating a new SSL certificate template named "**Web-SSL**" based on the "Web Server" template, ensuring it supported digital signature and key encipherment with a **minimum key size of 2048**. Permissions were set to allow Domain Computers to autoenroll. The CA service was restarted, an SSL/TLS certificate was requested and issued for a domain controller (e.g., `dc115.vlabs15.com`), and the certificate was **bound to the local Internet Information Services (IIS) web server**.
*   **Testing and verifying HTTPS access** to the secured web server, confirming that the connection was secure using the newly issued SSL certificate.

**Skills Demonstrated:**
*   **Active Directory (AD) Management**.
*   **Certificate Authority (CA) Administration** (Enterprise CA setup, certificate issuance).
*   **Certificate Template Customization** (User, Digital Signature, SSL/TLS).
*   **Group Policy Object (GPO) Configuration** (for automatic certificate enrollment).
*   **Digital Certificates Lifecycle Management**.
*   **SSL/TLS Security Implementation**.
*   **Internet Information Services (IIS) Configuration** (SSL binding).
*   **Cryptography Fundamentals** (key usage, key size, digital signatures).
*   **Windows Server Administration**.

#### **4. Apache Virtual Host Configuration**

**Description:**
This project involved the **advanced configuration of an Apache web server to host multiple virtual websites**, demonstrating various methods of virtual hosting including name-based, port-based, and dynamic configurations, along with access controls. Key tasks included:
*   **Preparing the web server environment** by setting `/var/www/html_project2` as the root directory and `master_project2.html` as the default page, which contained hyperlinks for testing all configured virtual hosts and scenarios.
*   Configuring **name-based and port-based virtual hosts** that shared the same IP address (10.35.16.1) but differentiated by hostname and port numbers. This included `virtual1.aucegep.com` and `virtual2.aucegep.com` accessible on both port 80 and port 8000, requiring adjustments to SELinux port contexts and host file entries.
*   Implementing **name-based virtual hosts with access control** using IP 10.35.17.1 for:
    *   `www.ici.com` (port 80) and `intranet.ici.com` (port 80), both accessible to everyone.
    *   `intranet.ici.com` (port 8000) and `development.ici.com` (port 80), both accessible only from the **10.35.17.0/24 subnet**.
*   Creating **virtual web servers differentiated solely by IP address and port number** on IP 10.35.16.1. Four distinct servers were configured: "Sales" on port 8080, "Admin" on port 8081, "Thing" on port 8082, and "Other" on port 8083. This also required proper SELinux port configuration and log file management.
*   Setting up **dynamic virtual hosting** using a single `<VirtualHost>` block and the `VirtualDocumentRoot` directive for multiple domains (e.g., `www.itmt.com`, `www.itmt.ca`, `www2.itmt.com`, `www.montmo.com`, `www.montmo.ca`) all resolving to IP 10.50.1.1. The directory structure was dynamically generated based on the domain's Top-Level Domain (TLD), company name, and prefix, with all errors logged to a central file (`/var/www/virtuals/q5/logs/virtual_error_q5_log`).
*   Thoroughly **testing all virtual host configurations** from various client IP addresses and subnets to verify correct access and functionality.

**Skills Demonstrated:**
*   **Apache Virtual Host Configuration** (name-based, port-based, dynamic).
*   **DNS Management** (host file configuration).
*   **Network Port Management** and **SELinux Configuration**.
*   **Directory Structuring** for complex web environments.
*   **IP-Based Access Control**.
*   **Web Server Troubleshooting**.
*   **Linux Command Line Interface (CLI)** for system and Apache configuration.

---

### **Key Technologies & Skills Demonstrated Across Projects**

These projects collectively highlight a broad range of skills critical for web server and infrastructure management:

*   **Operating Systems:** Linux (AlmaLinux, Ubuntu), Windows Server 2019.
*   **Web Servers:** **Apache HTTP Server** (Installation, Configuration, Optimization, Security).
*   **Network Services:** **Active Directory**, DNS, DHCP, SSL/TLS, HTTPS.
*   **Security:** **Certificate Authority (CA)** administration, Digital Certificates (User, Digital Signature, Web Server), Group Policy Objects (GPO) for certificate enrollment, **Apache Security (Authentication, Authorization, Access Control Lists)**, SELinux.
*   **Scripting & Programming:** **PHP**, Perl (CGI).
*   **Databases:** **MySQL** (Installation, Database/Table Management, PHP Integration).
*   **Web Technologies:** HTML, CSS.
*   **Server Management:** Multi-Process Modules (MPM), Server Monitoring (server-status, server-info), **Virtual Hosting (Name-based, Port-based, Dynamic)**, Apache Aliases, IIS Configuration.
*   **Tools & Utilities:** `httpd.conf`, `.htaccess`, `htpasswd`, `openssl`, `dnf`, `systemctl`, `semanage`, `chcon`, `setsebool`, `nmcli`, `certsrv`, `inetmgr`, `iisreset`, MMC.

---

### **Usage / How to Recreate (High-Level)**

These projects were developed in **virtual lab environments** and represent specific configurations and demonstrations rather than standalone applications.

*   The **Apache projects** (`Apache Optimization & Scripting`, `Apache Web Server Installation and Advanced Security Configuration`, `Apache Virtual Host Configuration`) are primarily based on **AlmaLinux** servers and involve extensive configuration of Apache's `httpd.conf` file, creation of `.htaccess` files, and management of directories and permissions via the **Linux command-line interface (CLI)**. They also include integration with PHP and MySQL.
*   The **Active Directory project** (`Managing a Certificate Authority Server in Active Directory`) involves configuring a **Windows Server 2019** machine to act as a Domain Controller and Certificate Authority, utilizing its **Graphical User Interface (GUI)** tools such as `certsrv` and `Group Policy Management Editor`, and demonstrating **IIS (Internet Information Services)** SSL binding.
*   Testing of these configurations involves accessing the web servers from different client machines (e.g., Ubuntu) and IP subnets to verify the implemented access controls and functionality.

Due to their nature as lab exercises with specific virtual network setups, direct execution instructions for this GitHub repository are not provided. However, the detailed descriptions and demonstrated configurations serve as a comprehensive guide for anyone looking to understand or replicate similar infrastructure projects.

---
