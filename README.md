
#STEP-1: Increase /tmp storage (Fix space issue)
sudo mount -o remount,size=2G /tmp

#STEP-2: Install Git and Maven
sudo yum install git maven -y

#STEP-3: Add Jenkins Repository
sudo wget -O /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/redhat-stable/jenkins.repo

#STEP-4: Import Jenkins Key
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

#STEP-5: Install Java 21
sudo yum install java-21-amazon-corretto -y

#STEP-6: Install Jenkins
sudo yum install jenkins -y

#STEP-7: Start Jenkins Service
sudo systemctl start jenkins

#STEP-8: Check Jenkins Status
sudo systemctl status jenkins

#STEP-9: Enable Jenkins Auto Start
sudo systemctl enable jenkins
