pipeline {
    agent any  // Runs on any available agent
 
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/Sudhanshumishraa/OTeaching.git'  // Replace with your repo URL
            }
        }
 
        stage('Build') {
            steps {
                script {
                    // Example for a .NET Core application
                    bat 'dotnet build --configuration Release'
                }
            }
        }
 
        stage('Test') {
            steps {
                script {
                    bat 'dotnet test --no-build --configuration Release'
                }
            }
        }
 
        stage('Publish') {
            steps {
                script {
                    bat 'dotnet publish -c Release -o publish'
                }
            }
        }
 
        stage('Deploy') {
            steps {
                script {
                    // Example for IIS deployment on a remote server
                    bat 'scp -r publish C:\ProgramData\Jenkins\.jenkins\workspace\Oteacting_build'
                }
            }
        }
    }
}
 
 
