pipeline {
    agent any

    tools{
        maven 'Maven3'
    }

    stages {
        stage('Cleanup Workspace'){
            steps{
                cleanWs()
            }
        }

        stage('Checkout from SCM'){
            steps{
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/yusufal-dev/cicdSCM.git'
            }
        }

        stage('Build Application'){
            steps{
                sh 'mvn clean package'
            }
        }

        stage('Test Application'){
            steps{
                sh 'mvn test'
            }
        }

    }
}