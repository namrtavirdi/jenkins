pipeline {
    agent any

    stages {

        stage('Deploy Dev') {
            when {
                branch 'dev'
            }
            steps {
                bat '''
                xcopy /E /I /Y dev\\* C:\\Deploy\\Dev\\
                '''
            }
        }

        stage('Deploy Main') {
            when {
                branch 'main'
            }
            steps {
                bat '''
                xcopy /E /I /Y main\\* C:\\Deploy\\Main\\
                '''
            }
        }
    }
}