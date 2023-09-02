/* Requires the Docker Pipeline plugin */
pipeline {
    agent any //{ docker { image 'python:3.11.5-alpine3.18' } }
    environment {
        SECRET_TEXT = credentials('MySecretText')
    }
    stages {
        stage('build') {
            steps {
                bat 'echo "IM IN"'
                timeout(time: 1, unit: "SECONDS"){
                    retry(3){
                        bat 'echo "(SECRET_TEXT)" >> NewFile.txt'
                    }
                }
            }
        }
    }

    post{
        success{
            echo "Getting there"
        }

        failure{
            echo "Try again"
        }
    }
}
