pipeline {
    agent any

    parameters {
        choice(
            name: 'BRANCH',
            choices: ['main', 'dev', 'test'],
            description: 'Select branch to deploy'
        )
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: params.BRANCH,
                    credentialsId: 'GitHub Deploy',
                    url: 'https://github.com/namrtavirdi/jenkins.git'
            }
        }

        stage('Display Content') {
            steps {
                script {
                    echo "Current Branch: ${params.BRANCH}"

                    if (params.BRANCH == 'main') {
                        bat '''
                        echo ===== MAIN BRANCH =====
                        type main\\index.txt
                        '''
                    }
                    else if (params.BRANCH == 'dev') {
                        bat '''
                        echo ===== DEV BRANCH =====
                        type dev\\index.txt
                        '''
                    }
                    else if (params.BRANCH == 'test') {
                        bat '''
                        echo ===== TEST BRANCH =====
                        type test\\index.txt
                        '''
                    }
                }
            }
        }
    }
}
