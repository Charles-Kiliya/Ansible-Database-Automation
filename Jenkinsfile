pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'ansible-galaxy install -r requirements.yml'
                sh 'ansible-playbook -i hosts -v playbook.yml'
            }
        }
        stage('Test') {
            steps {
                sh 'ansible-playbook -i hosts -v playbook.yml --check'
            }
        }
        stage('Deploy') {
            steps {
                sh 'ansible-playbook -i hosts -v playbook.yml'
            }
        }
    }
}
