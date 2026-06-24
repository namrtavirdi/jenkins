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

                    def branch = env.GIT_BRANCH

                    echo "Current Branch: ${branch}"

                    if (branch.contains("main")) {
                        bat '''
                        echo ===== MAIN BRANCH =====
                        type main\\index.txt
                        '''
                    }

                    if (branch.contains("dev")) {
                        bat '''
                        echo ===== DEV BRANCH =====
                        type dev\\index.txt
                        '''
                    }
                }
            }
        }
    }
}
