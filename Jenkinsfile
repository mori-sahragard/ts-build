pipeline {
    agent any
    environment {
        VERSION = "0.1.0"        
        VERSION_RC = "rc.2"
    }
    stages {
        stage('Audit tools') {                        
            steps {
                sh '''
                  git version
                  npm --version
                  docker version
                  dotnet --list-sdks
                  dotnet --list-runtimes
                '''
            }
        }
        stage('Build') {
            steps {
              echo "Building version: ${VERSION} with suffix: ${VERSION_RC}"
              sh 'npm i'
            }
        }
    }
}
