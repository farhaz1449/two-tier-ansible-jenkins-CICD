pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/farhaz1449/two-tier-ansible-jenkins-CICD.git'
            }
        }
        stage('Run Backend Playbook') {
            steps {
                ansiblePlaybook playbook: 'back-playbook.yml', inventory: 'hosts'
            }
        }
        stage('Run Frontend Playbook') {
            steps {
                ansiblePlaybook playbook: 'front-playbook.yml', inventory: 'hosts'
            }
        }
    }
    post {
        success {
            echo 'Pipeline execution successful.'
        }
        failure {
            echo 'Pipeline execution failed.'
        }
    }
}