def frontendImage="Pawel7710/frontend"
def backendImage="Pawel7710/backend"
def dockerRegistry=""
def registryCredentials="dockerhub"
def backendDockerTag=""
def frontendDockerTag=""


pipeline {
parameters {
  string 'backendDockerTag'
  string 'frontenDockerTag'
}

    agent {
        label 'agent'
    }

    stages {
        stage('Get Code') {
            steps {
                checkout scm
            }
        }
        stage('Adjust version') {
            steps {
                script{
                    backendDockerTag = params.backendDockerTag.isEmpty() ? "latest" : params.backendDockerTag
                    frontendDockerTag = params.frontendDockerTag.isEmpty() ? "latest" : params.frontendDockerTag
                    currentBuild.description = "Backend: ${backendDockerTag}, Frontend: ${frontendDockerTag}"
                }
            }
    }
}