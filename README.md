
# SonarQube Installation and Configuration Guide

## Steps to Install and Configure SonarQube on Ubuntu

### 1. Extract SonarQube Package
```bash
cd /opt/
unzip sonarqube-10.4.1.88267.zip
sudo mv sonarqube-10.4.1.88267 sonarqube
```

### 2. Set Proper Ownership
```bash
sudo chown -R ubuntu:ubuntu sonarqube
```

### 3. Start SonarQube Server
```bash
cd sonarqube/bin/linux-x86-64/
sudo ./sonar.sh start
sudo ./sonar.sh status
```

### 4. Install Java (OpenJDK 17)
```bash
sudo apt install openjdk-17-jre-headless -y
```

### 5. Check Running Services
```bash
sudo apt install net-tools
sudo netstat -ntpl
```

---

## Maven Project Configuration with SonarQube

### 1. Install Maven
```bash
sudo apt install maven -y
```

### 2. Clone Your Java Project
```bash
git clone https://github.com/daniyel7devops/docker-Java-kubernetes-project.git
cd docker-Java-kubernetes-project/productcatalogue/
```

### 3. Run SonarQube Analysis
```bash
mvn clean verify sonar:sonar   -Dsonar.projectKey=my-project   -Dsonar.host.url=http://98.84.180.157:9000   -Dsonar.login=sqa_0d1d2430f8e629a45dc4e65db5938e66c0c70149
```

---

## Install SonarScanner (Optional CLI Tool)
```bash
wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-5.0.1.3006-linux.zip
unzip sonar-scanner-5.0.1.3006-linux.zip
sudo mv sonar-scanner-5.0.1.3006-linux /opt/sonar-scanner
echo 'export PATH=$PATH:/opt/sonar-scanner/bin' >> ~/.bashrc
source ~/.bashrc
```

---

## SonarQube Project Dashboard Screenshot
*(Include your screenshot here if applicable.)*
