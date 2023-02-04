pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat '''mvn compile
                       mvn package'''
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                bat '''mvn test'''
                echo 'Test Success'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post
    {
        always
        {
            emailext body: 'Build javaMaven Project Failure', subject: 'Pipeline status', to: 'abdou.karim.info@gmail.com'
        }
    }
}

