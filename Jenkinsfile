pipeline {
    agent any
    tools {
        dotnet '6.0'
    }
    stages {
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
