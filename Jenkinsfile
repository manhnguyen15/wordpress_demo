pipeline {

    agent any

    environment {
        BUILD_PATH = '/var/lib/jenkins/workspace/Deploy_on_Container_using_ansible'
    }

    stages {

        stage('Build') {
            steps {
              sh '''
                ansible-playbook -i $BUILD_PATH/inventory.yml $BUILD_PATH/playbook-build-image.yml
              '''
            }
        }

        stage('Deploy') {
            steps {
              sh '''
                ansible-playbook -i $BUILD_PATH/inventory.yml $BUILD_PATH/playbook-deploy.yml
              '''
            }
        }
    }
}
