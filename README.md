# Medical Chatbot with Generative AI

Welcome to the **Medical Chatbot with Generative AI** project! This chatbot leverages **GPT, LangChain, Pinecone, and Flask** to provide intelligent medical responses based on embeddings and real-time queries.

## 🚀 Features
- AI-powered medical chatbot for intelligent Q&A
- Uses **LangChain** for efficient query handling
- **Pinecone** for vector-based search & indexing
- Deployed using **AWS EC2, ECR, and GitHub Actions**
- Built with **Python, Flask, and OpenAI GPT models**

---
## 📥 Clone the Repository
```bash
 git clone https://github.com/YOUR-REPO-LINK.git
 cd YOUR-REPO-NAME
```

---
## 🛠 Setup & Installation
### Step 1: Create a Virtual Environment
```bash
conda create -n medibot python=3.10 -y
conda activate medibot
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 3: Configure Environment Variables
Create a `.env` file in the root directory and add your **Pinecone & OpenAI credentials**:
```plaintext
PINECONE_API_KEY = "your_pinecone_api_key"
OPENAI_API_KEY = "your_openai_api_key"
```

### Step 4: Store Embeddings in Pinecone
```bash
python store_index.py
```

### Step 5: Run the Application
```bash
python app.py
```

Now, open your browser and go to **`http://localhost:5000`** 🎉

---
## 🌐 Deployment on AWS with GitHub Actions

### **1️⃣ AWS Setup**
- **Login to AWS Console**
- **Create an IAM User** with the following permissions:
  - AmazonEC2FullAccess
  - AmazonEC2ContainerRegistryFullAccess

### **2️⃣ AWS Services Used**
- **EC2**: Virtual Machine to host the application
- **ECR**: Store & manage Docker images

### **3️⃣ Deployment Workflow**
1. **Build a Docker image** of the source code
2. **Push the Docker image to AWS ECR**
3. **Launch an EC2 instance** (Ubuntu)
4. **Pull the image from ECR to EC2**
5. **Run the containerized chatbot in EC2**

### **4️⃣ Create an ECR Repository**
```bash
aws ecr create-repository --repository-name medicalchatbot
```
> Save the **URI**: `970547337635.dkr.ecr.ap-south-1.amazonaws.com/medicalchatbot`

### **5️⃣ Setup EC2 & Install Docker**
```bash
sudo apt-get update -y
sudo apt-get upgrade -y
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

### **6️⃣ Configure EC2 as a GitHub Self-Hosted Runner**
1. Go to **GitHub Repository** → **Settings** → **Actions** → **Runners**
2. Select **New Self-Hosted Runner** → Choose OS → Run the given commands

### **7️⃣ Set Up GitHub Secrets**
Store the following credentials in **GitHub Actions → Secrets**:
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_DEFAULT_REGION`
- `ECR_REPO`
- `PINECONE_API_KEY`
- `OPENAI_API_KEY`

---
## 🏆 Tech Stack
- **Python** 🐍
- **LangChain** 🏗️
- **Flask** 🌐
- **GPT (OpenAI API)** 🤖
- **Pinecone (Vector Database)** 🏢
- **AWS EC2, ECR** ☁️
- **GitHub Actions (CI/CD)** ⚙️

---
## 📜 License
This project is licensed under the **MIT License**.

---
## 📩 Contact & Support
For any queries or suggestions, feel free to reach out!

🔹 **Author:** SAHIL PAWAR  
🔹 **Email:** sahilypawar9192@gmail.com 
🔹 **GitHub:** [Sahil9192](https://github.com/Sahil9192)  

---
💡 *Happy Coding! 🚀*

