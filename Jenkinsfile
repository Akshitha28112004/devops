pipeline { 
 agent any 
 stages { 
  stage('Clone Repository') { 
   steps { 
   git url: 'https://github.com/Akshitha28112004/devops.git', branch: 'main'  } 
   } 
   stage('Build Docker Image') { 
   steps { 
   bat 'docker build -t register:v1 .' 
   } 
   } 
   stage('Run Docker Container') { 
   steps { 
   bat 'docker rm -f registration-container || exit 0' 
   bat 'docker run -d -p 5001:5000 --name registration-container  register:v1' 
   } 
   } 
  stage('Automated UI Test') {
            steps {
                bat 'python C:\DevOps\week-2\test_registration.py'
            }
        }

  } 
}
