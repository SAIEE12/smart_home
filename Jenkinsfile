pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/SAIEE12/smart_home.git'
            }
        }

        stage('Build') {
            steps {
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
