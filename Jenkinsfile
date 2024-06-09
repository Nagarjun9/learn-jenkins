pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        // Timeout counter starts AFTER agent is allocated 
        timeout(time:1, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo This is Build'
                sh 'sleep 10'
            }
        }
        stage('Tests') {
            steps {
                sh 'echo This is Test'
            }
        }
        stage('Deploy') {
            steps {
                 sh 'echo This is Deploy'
           }
       }
       stage('print param') {
        steps {
            echo "Hello: ${param.PERSON}"
            echo "Biography: ${param.BIOGRAPHY}"
            echo "Toggle: ${param.TOGGLE}"
            echo "Choice: ${param.CHOICE}"
            echo "Password: ${param.PASSWORD}"
        }
       }
   }
}