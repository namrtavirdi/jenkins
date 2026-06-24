pipeline {
    agent any

    parameters {
        choice(
            name: 'BRANCH',
            choices: ['main', 'dev'],
            description: 'Select branch'
        )
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: params.BRANCH,
                    url: 'https://github.com/namrtavirdi/jenkins.git'
            }
        }

        stage('Display Content') {
            steps {
                sh '''
                echo "Current Branch: ${BRANCH}"

                if [ "$BRANCH" = "main" ]; then
                    echo "===== Main Branch Content ====="
                    cat main/index.txt
                fi

                if [ "$BRANCH" = "dev" ]; then
                    echo "===== Dev Branch Content ====="
                    cat dev/index.txt
                fi
                '''
            }
        }
    }
}
