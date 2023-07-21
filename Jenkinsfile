pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'sudo scp -r /var/lib/jenkins/workspace/demo_webpage/* 172.31.33.253:/opt/web_page/'
                sh 'sudo ssh -o StrictHostKeyChecking=no 172.31.33.253 ansible-playbook -i host web.yaml'
            }
        }
    }
}
