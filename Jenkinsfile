pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
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
