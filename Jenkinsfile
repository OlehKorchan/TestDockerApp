pipeline {
    agent any
    tools {
       msbuild 'msbuild-16.0' // assumes the MSBuild tool has been added as a tool in Jenkins
    }
    stages {
        stage('Restore Packages') {
            steps {
                sh 'nuget restore'
            }
        }
        stage('Build') {
            steps {
                sh 'msbuild /t:Build /p:Configuration=Release'
            }
        }
    }
}
