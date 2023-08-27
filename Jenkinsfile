/* Requires the Docker Pipeline plugin */
pipeline {
    agent any //{ docker { image 'python:3.11.5-alpine3.18' } }
    stages {
        stage('build') {
            steps {
                timeout(time: 1, unit: "SECONDS"){
                    for(int i=0; i<100; i++){
                        echo "IM IN"
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
