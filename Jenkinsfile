pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 130, unit: 'SECONDS')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment {
        DEPLOY_TO = 'producation'
        GREETING = 'Good Morning'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo This is Build'
                sh 'sleep 10'
                sh 'env'

            }
        }
        stage('Test') {
            steps {
                sh 'echo this is Test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo this is Deploy' 
            }
        }
        stage('print param') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
            }
        post {
            always {
                echo 'I will always say Hello again'
            }
            success {
                echo 'its run when job success'
            }
            failure {
                echo 'its run when job failers'
            }
        }
        }
        
    }
}






// pipeline {
//     agent {
//         label 'AGENT-1'
//     }
//     options {
//         // Timeout counter starts AFTER agent is allocated 
//         timeout(time:1, unit: 'MINUTES')
//         disableConcurrentBuilds()
//     }
//     parameters {
//         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//         text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//         booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
//         choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
//         password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
//     }
//     environment{
//         DEPLOY_TO = 'producation'
//         GREETING = 'good morning'
//     }
//     stages {
//         stage('Build') {
//             steps {
//                 sh 'echo This is Build'
//                 sh 'sleep 10'
//                 sh 'env'
//             }
//         }
//         stage('Tests') {
//             steps {
//                 sh 'echo This is Test'
//             }
//         }
//         stage('Deploy') {
//             steps {
//                  sh 'echo This is Deploy'
//            }
//        }
//        stage('print param') {
//             steps {
//                 echo "Hello ${params.PERSON}"
//                 echo "Biography: ${params.BIOGRAPHY}"
//                 echo "Toggle: ${params.TOGGLE}"
//                 echo "Choice: ${params.CHOICE}"
//                 echo "Password: ${params.PASSWORD}"
//            }
//        }
       
//        }
//        post {
//         always {
//             echo 'I will always say Hellow again'
//         }
//         success {
//             echo 'I will run when pipeline is success'
//         }
//         //failure {
//         //   echo 'I will run when pipeline is failed'
//         //}
//    }
// }