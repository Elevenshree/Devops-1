 **DevOps Learning Summary**

 Session 1: Jenkins & Tomcat Deployment**
- **Plugins Setup in Jenkins**
  - Installed and used the **"Deploy to container"** plugin via the **Manage Jenkins** > **Plugins** section.

- **Java Web App Deployment Steps**
  1. **WAR File Creation**: Built the Java app (`EcommerceApp.war`) using Jenkins.
  2. **Manual Extraction**:
     - Moved WAR file to Tomcat’s `webapps/` folder.
     - Extracted WAR using:  
       ```bash
       sudo unzip EcommerceApp.war -d EcommerceApp/
       ```
  3. **Restart Tomcat**:  
     ```bash
     sudo ./catalina.sh stop  
     sudo ./catalina.sh start
     ```
  4. **App Access**:  
     Accessed via: `http://localhost:8080/EcommerceApp/`

- **Key Learnings**
  - Manual WAR deployment and troubleshooting
  - Tomcat behavior with WAR files
  - Jenkins + Tomcat integration
  - Restarting services via CLI

 Session 2: Cloud Concepts & Linux Server Basics**
- **Cloud Computing Overview**
  - Cloud = Remote service delivery
  - **Data Centers in India**: Mumbai, Hyderabad
  - **Service Models**: IaaS, PaaS, SaaS
  - AWS provides high availability and auto-scaling

- **AWS Compute Services**
  - EC2, EKS (Elastic Kubernetes Service)
  - Requires VPC (Virtual Private Cloud) to deploy

- **Linux Server Essentials**
  - OS Families: Red Hat (RHEL, Amazon Linux), Debian (Ubuntu)
  - **Important Services**: `httpd` (daemon for Apache), Nginx
  - **Commands**:
    ```bash
    chmod 400 key.pem  
    ssh -i "key.pem" ec2-user@<public-ip>  
    sudo su  
    yum install httpd git -y  
    git clone <repo-url>  
    cp -r . /var/www/html  
    service httpd start  
    ```

 Session 3: Terraform & AWS Automation**
- **Terraform = Infrastructure as Code (IaC)**
  - Used to automate resource creation (EC2, VPC, Subnets, etc.)
  - **Terraform Setup**:
    - Install Terraform & AWS CLI
    - Configure AWS credentials
  - **Terraform Script Blocks**:
    1. **Provider**: Define cloud provider
    2. **Resource**: EC2, Load balancer, etc.
    3. **Variable**: Input parameters
    4. **Output**: Print useful info like IPs
  - **Essential EC2 Parameters**:
    - AMI ID, Instance Type, Key Name, Storage, Instance Name
    - Run with `terraform plan` and `terraform apply`

 Session 4: Docker & Microservices**
- **Docker Basics**
  - OS-level virtualization
  - Enables platform-independent, portable apps
  - Each microservice has its own Dockerfile, image, container
- **Monolithic vs Microservices**
  - **Monolithic**: Single-tier app; tightly coupled; single point of failure
  - **Microservices**: Independently deployable services; loosely coupled
  - **Advantages**:
    - Fault isolation
    - Scalability
    - “Build Once, Run Anywhere”

Session 5: Kubernetes (K8s)**
- **Kubernetes Overview**
  - Container orchestration tool
  - Solves Docker limitations (no autoscaling, load balancing, etc.)

- **Kubernetes Features**
  1. Orchestration
  2. Autoscaling
  3. Load balancing
  4. Self-healing

- **Kubernetes Cluster**
  - **Master Node**: API Server, etcd (DB), Controller, Scheduler
  - **Worker Node**: Kubelet, Container Runtime, kube-proxy
  - **Pod**: Smallest deployment unit (contains containers)

- **Types of Clusters**:
  - **On-Premises**: Self-managed
  - **Cloud-Managed**: Managed by providers like AWS EKS

- **Manifest Files**:
  - Use YAML to define resources
  - Includes fields like `apiVersion`, `kind`, `metadata`, `spec`

