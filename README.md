# 📦 DevOps Assignment – Flask App with CI/CD, Docker, Terraform, and Monitoring

This project is a complete DevOps pipeline that deploys a Python Flask API using Docker, GitHub Actions for CI/CD, Terraform for Infrastructure as Code (IaC), and basic system monitoring for CPU usage.

---

## 🚀 Features

- Containerized Flask app with Docker
- Automated CI/CD pipeline using GitHub Actions
- Infrastructure provisioning with Terraform (e.g., AWS EC2 instance)
- CPU usage monitoring and basic alerts
- Clean folder structure with deployment scripts

---

## 📁 Project Structure

Assignment/ ├── app/ # Flask application │ ├── app.py │ └── requirements.txt ├── Dockerfile # Docker build file ├── .github/ │ └── workflows/ │ └── deploy.yml # GitHub Actions workflow ├── terraform/ │ ├── main.tf │ ├── variables.tf │ └── outputs.tf ├── deploy.sh # Optional: Manual deployment script ├── README.md └── .gitignore


---

✅ Full README.md 

# 📦 DevOps Assignment – Flask App with CI/CD, Docker, Terraform, and Monitoring

This project is a complete DevOps pipeline that deploys a Python Flask API using Docker, GitHub Actions for CI/CD, Terraform for Infrastructure as Code (IaC), and basic system monitoring for CPU usage.

---

## 🚀 Features

- Containerized Flask app with Docker
- Automated CI/CD pipeline using GitHub Actions
- Infrastructure provisioning with Terraform (e.g., AWS EC2 instance)
- CPU usage monitoring and basic alerts
- Clean folder structure with deployment scripts

---

## 📁 Project Structure

Assignment/ ├── app/ # Flask application │ ├── app.py │ └── requirements.txt ├── Dockerfile # Docker build file ├── .github/ │ └── workflows/ │ └── deploy.yml # GitHub Actions workflow ├── terraform/ │ ├── main.tf │ ├── variables.tf │ └── outputs.tf ├── deploy.sh # Optional: Manual deployment script ├── README.md └── .gitignore

yaml
Copy
Edit

---

## 🔧 How to Use

### 1. Clone the Repository

```bash
git clone https://github.com/Akshay Mehtaa/assignment.git
cd assignment

2. Run the App Locally with Docker

docker build -t flask-app .
docker run -p 5000:5000 flask-app
Then open: http://localhost:5000

3. Set Up GitHub Secrets (for CI/CD)

Go to your GitHub repo → Settings → Secrets → Actions → Add these:


4. GitHub Actions Pipeline
On every push to main, GitHub will:

Build and push Docker image

SSH into VM and deploy the latest container

5. Terraform IaC Deployment
Navigate to the Terraform folder and run:

cd terraform
terraform init
terraform apply
This will:

Launch a virtual machine

Open necessary ports (5000, 22)

Install Docker and run the container

6. Monitoring & Alerts
Basic monitoring script runs on the server to alert if CPU usage > 70%:

CPU=$(top -bn1 | grep "Cpu(s)" | awk '{print $2 + $4}')
if (( $(echo "$CPU > 70.0" | bc -l) )); then
  echo "CPU usage is high: $CPU%" | mail -s "CPU Alert" your@email.com
fi
Schedule this with cron for regular checks.


🙋‍♂️ Author
[Akshay Mehta]
GitHub: https://github.com/Mrakshaymehta



📚 Tech Stack
🐍 Python + Flask

🐳 Docker

🔁 GitHub Actions

☁️ Terraform (AWS)

🧠 Bash, SSH, Cron (Monitoring)
