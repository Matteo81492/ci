/* Requires the Docker Pipeline plugin */
pipeline {
    agent any //{ docker { image 'python:3.11.5-alpine3.18' } }
    environment {
        SECRET_TEXT = credentials('MySecretText')
        SECRET_TEXT2 = SECRET_TEXT
    }
    stages {
        stage('build') {
            steps {
                bat 'echo "IM IN"'
                timeout(time: 1, unit: "SECONDS"){
                    retry(3){
                        bat 'echo "IM IN $(SECRET_TEXT2)"'
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
