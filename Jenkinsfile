pipeline {

    agent {

        docker {image 'horuszup/horusec-cli:latest'}
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

                    sh 'horusec start -p="./" --disable-docker="true" --config-file-path=horusec-config.json -a 832a4660-b5c6-4880-b886-b8d94f2fb765'

                }

            }

        }

    }

}
