pipeline {
    agent {
        node {
            label 'jenkins-agent'
        }
    }
    environment{
        COURSE="Jenkins"
    }
    options{
        timeout(time: 10, unit:'SECONDS')
    }
    stages {
        stage('Build') {
            steps {
                script{
                    sh """
                    echo "This is the build stage"
                    echo $COURSE
                    sleep 10
                    env
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script{
                    sh """
                    echo "This is the test stage"
                    echo $COURSE
                    """
                }
            }
        }
        stage('Deploy') {
            steps {
                script{
                    sh """
                    echo "This is the Deploy stage"
                    echo $COURSE
                    """
                }
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
        aborted{
            echo "This is aborted"
        }
    }
}