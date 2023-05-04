pipeline {
    agent any
    tools {
        dotnet '6.0'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          extensions: [[$class: 'CleanBeforeCheckout']],
                          userRemoteConfigs: [[url: 'https://github.com/OlehKorchan/TestDockerApp.git']]])
            }
        }
        stage('Restore Packages') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build -c Release'
            }
        }
        stage('Publish') {
            steps {
                sh 'dotnet publish -c Release -o ./publish'
            }
        }
    }
}
