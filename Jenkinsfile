pipeline {
    agent any

    triggers {
        pollSCM('* * * * *') // Polls SCM every minute
    }

    stages {
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Execute Tests') {
            steps{
                bat 'dotnet test --no-build --verbosity normal'
        }
    }
}
