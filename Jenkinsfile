pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                echo 'checking files from github'
            }
        }
        stage('check_app') {
            steps {
                sh 'cat index.html'
                sh 'whoami'
            }
        }
        stage('install dep') {
            steps {
                sh 'sudo yum update -y'
                sh 'sudo yum install -y httpd'
                sh 'sudo systemctl start httpd'
                sh 'sudo systemctl enable httpd'
                sh 'sudo cp index.html /var/www/html/index.html'
            }
        }  
        stage('status_app') {
            steps {
                sh 'netstat -tuln | grep 80'
            }
        }              
    }
}
