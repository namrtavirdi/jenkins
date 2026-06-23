pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: params.BRANCH,
                    url: 'https://github.com/namrtavirdi/jenkins.git'
            }
        }

        stage('Deploy') {
            steps {
                script {

                    if (params.BRANCH == 'main') {
                        bat 'xcopy /E /I /Y main\\* C:\\Deploy\\Main\\'
                    }

                    if (params.BRANCH == 'dev') {
                        bat 'xcopy /E /I /Y dev\\* C:\\Deploy\\Dev\\'
                    }
                }
            }
        }
    }
}
