pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Cloner le référentiel Ansible
                git 'https://github.com/votre-repo-ansible.git'
            }
        }
        stage('Deploy Database') {
            steps {
                // Exécuter le playbook Ansible pour déployer la base de données
                sh 'ansible-playbook -i inventory playbook.yml'
            }
        }
        stage('Monitor Database') {
            steps {
                // Exécuter des tâches de surveillance de la base de données
                sh 'ansible-playbook -i inventory monitor.yml'
            }
        }
    }
}

