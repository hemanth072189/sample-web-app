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
            }
        }
        stage('install dep) {
            steps {
                sh 'sudo yum update -y'
                sh 'sudo yum install -y httpd'
                sh 'systemctl start httpd'
                sh 'systemctl enable httpd'
                sh 'cp index.html /var/www/html/index.html'
            }
        }  
        stage('status_app') {
            steps {
                sh 'netstat -tuln | grep 80'
            }
        }              
    }
}
