pipeline {
    agent any

    options {
        skipDefaultCheckout() // avoid auto-clone
    }

    stages {
        stage('Cleanup Workspace') {
            steps {
                deleteDir() // Jenkins pipeline built-in workspace cleanup
            }
        }

        stage('Checkout') {
            steps {
                git 'https://github.com/SAIEE12/smart_home.git'
            }
        }

        stage('Build') {
            steps {
                sh 'make clean || true'
                sh 'make'
            }
        }

        stage('Test') {
            steps {
                sh './test_lights_control'
                sh './test_temperature_control'
            }
        }
    }
}
