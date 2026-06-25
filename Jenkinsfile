pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Display Content') {
            steps {
                script {
                    echo "Current Branch: ${env.BRANCH_NAME}"

                    if (env.BRANCH_NAME == 'main') {
                        bat 'type main\\index.txt'
                    }
                    else if (env.BRANCH_NAME == 'dev') {
                        bat 'type dev\\index.txt'
                    }
                    else if (env.BRANCH_NAME == 'test') {
                        bat 'type test\\index.txt'
                    }
                }
            }
        }
    }
}
