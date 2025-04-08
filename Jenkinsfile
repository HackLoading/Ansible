pipeline {
    agent any

    tools {
        ansible 'Ansible-Installation'  // Must match name in Jenkins -> Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/youraccount/your-repository.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    playbook: 'site.yml',
                    inventory: 'inventory.ini',
                    credentialsId: 'host-credentials'
                )
            }
        }
    }
}
