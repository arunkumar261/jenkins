pipeline {
    //agent any                     // -------------> default agent
//agent which is created by us here we r declaring
    agent {
      node{
        label 'AGENT-1'
      }
    }
    stages {
        stage('DEV') {
            steps {
              echo "Hello this is DEV Stage"
            }
        }
        
         stage('QA-testing') {
            steps {
              echo "Hello this is QA-testing Stage"
            }
        }
        stage('UAT') {
            steps {
              echo "Hello this is UAT Stage"
            }
        }
        stage('SAT') {
            steps {
              echo "Hello this is SAT Stage"
            }
        }
         stage('PRE-PROD') {
            steps {
              echo "Hello this is PRE-PROD Stage"
            }
        }
         stage('PROD') {
            steps {
              echo "Hello this is PROD Stage"
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'this runs when pipeline is failed, used generally to send some alerts'
        }
        success{
            echo 'I will say Hello when pipeline is success'
        }
    }



}
