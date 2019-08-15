pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                echo 'Restoring..'
				bat 'dotnet restore webapi.sln'
            }
        }
        stage('Building') {
            steps {
                echo 'building..'
				bat 'dotnet build webapi.sln -p:Configuration=release -v:q'
            }
        }
        stage('Publish') {
            steps {
                echo 'Publish....'
				bat 'dotnet publish webapi.sln'
            }
        }
		 stage('Deploy') {
            steps {
                echo 'Deploying...'
				bat 'dotnet webapi/bin/Release/netcoreapp2.1/webapi.dll'
            }
        }
    }
}