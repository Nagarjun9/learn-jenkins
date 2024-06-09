pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        // Timeout counter starts AFTER agent is allocated 
        timeout(time:1, unit: 'SECONDS')
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
   }
}