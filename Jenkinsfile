pipeline {

    agent any

    stages {

        stage('Build') {
            steps {
              sh '''
                ansible-playbook -i inventory.yml playbook-build-image.yml
              '''
            }
        }

        stage('Deploy') {
            steps {
              sh '''
                ansible-playbook -i inventory.yml playbook-deploy.yml
              '''
            }
        }
    }
}
