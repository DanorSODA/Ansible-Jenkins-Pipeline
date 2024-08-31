# Installation Guide for Ansible-Jenkins-Pipeline

## Prerequisites

1. **Docker** and **Docker Compose** installed on your system.
2. **Jenkins** installed with:
   - Ansible plugin.
   - Git plugin.
3. **Ansible** installed on the Jenkins node.

## Setup Instructions

### Step 1: Clone the Repository

```bash
git clone https://github.com/DanorSODA/Ansible-Jenkins-Pipeline.git
cd Ansible-Jenkins-Pipeline
```

### Step 2: Build and Start Docker Containers from the docker folder

```bash
docker compose up -d --build
```

### Step 3: Access Jenkins

1.Open a web browser and go to http://localhost:8080.

2.Complete the Jenkins setup wizard.

### Step 4: Install Necessary Plugins

- Go to Manage Jenkins > Manage Plugins.
  Install the following plugins:

  Ansible
  Git

### Step 5: Create Multi-Branch Pipeline

1.Go to Jenkins dashboard and click on New Item.
2.Enter a name (e.g., Ansible-Remote-Host-Setup).
3.Choose Multi-Branch Pipeline.
4.Configure Git repository and set the script path to Jenkinsfile.

### Step 6: Run the Pipeline

 Run the Jenkins job manually or allow it to be triggered based on repository changes.
