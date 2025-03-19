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
                    sh 'scp -r publish user@your-server:/path/to/iis/site'
                }
            }
        }
    }
}
