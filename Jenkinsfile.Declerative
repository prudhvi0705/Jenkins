pipeline {
    agent {
        node {
            label 'jenkins-agent'
        }
    }
    stages {
        stage('Build') {
            steps {
                echo "This is the build stage"
            }
        }
        stage('Test') {
            steps {
                echo "This is the Test stage"
            }
        }
        stage('Deploy') {
            steps {
                echo "This is the Deploy stage"
            }
        }
    }

    post{
        always{
            echo "I Will run irrespective of result"
            cleanWs()
        }
        success{
            echo "This is success section"
        }

        failure{
            echo "This is failure section"
        }
    }
}