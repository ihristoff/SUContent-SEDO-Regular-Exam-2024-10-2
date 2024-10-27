pipeline {
    agent any

    stages {
        stage('Install dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Set up .NET') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run Unit Tests') {
            steps {
                bat 'dotnet test Homies.UnitTests/Homies.UnitTests.csproj --no-build --verbosity normal'
            }
        }
        stage('Run Integration Tests') {
            steps {
                bat 'dotnet test Homes.IntegrationTests/Homes.IntegrationTests.csproj --no-build --verbosity normal'
            }
        }
    }
}
