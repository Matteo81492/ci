/* Requires the Docker Pipeline plugin */
pipeline {
    agent none //{ docker { image 'python:3.11.5-alpine3.18' } }
    stages {
        stage('build') {
            steps {
                timeout(time: 1, unit: "SECONDS"){
                    echo "IM IN"
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
