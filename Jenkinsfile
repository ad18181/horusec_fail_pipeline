pipeline {

    agent {

        docker {image 'horuszup/horusec-cli:latest' 
                args '-v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):$(which docker)'
               }
    }

 

    stages {

        stage('Checkout') {

            steps {

                // Checkout code from the branch

                checkout scm

            }

        }

 

        stage('Code Analysis with Horusec') {

            steps {

                script {

                    sh 'horusec start -p="./" --config-file-path=horusec-config.json'

                }

            }

        }

    }

}
