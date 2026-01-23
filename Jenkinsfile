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
        timeout(time: 10, unit:'MINUTES')
        disableConcurrentBuilds()
    }
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    //This is the build
    stages {
        stage('Build') {
            steps {
                script{
                    sh """
                    echo "This is the build stage"
                    echo $COURSE
                    sleep 10
                    #env
                    echo "Hello ${params.PERSON}"
                    echo "Biography: ${params.BIOGRAPHY}"
                    echo "Toggle: ${params.TOGGLE}"
                    echo "Choice: ${params.CHOICE}"
                    echo "Password: ${params.PASSWORD}"
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