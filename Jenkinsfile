pipeline {
    agent any

    environment {
        DOTNET_CLI_TELEMETRY_OPTOUT = '1'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/Sudhanshumishraa/OTeaching.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Change directory if needed, or specify the .csproj file directly
                    // Example: bat 'dotnet build OTeachingApp/OTeachingApp.csproj --configuration Release'
                    bat 'dotnet build --configuration Release'
                }
            }
        }

        stage('Publish') {
            when {
                expression { currentBuild.currentResult == 'SUCCESS' }
            }
            steps {
                echo 'Publishing the build artifacts...'
                // Add your publish commands here
            }
        }

        stage('Deploy') {
            when {
                expression { currentBuild.currentResult == 'SUCCESS' }
            }
            steps {
                echo 'Deploying the application...'
                // Add your deploy commands here
            }
        }
    }

    post {
        failure {
            echo 'Build failed.'
        }
        success {
            echo 'Build succeeded.'
        }
    }
}
