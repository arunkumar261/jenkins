pipeline {
    //agent any                     // -------------> default agent
//agent which is created by us here we r declaring
    agent {
      node{
        label 'AGENT-1'
      }
    }
    environment{
      dev = "DEV"
      qa = "QA"
      prod = "PROD"
    }

    options{
        timeout(time:1, unit:'HOURS')
        disableConcurrentBuilds()
    }
 
     parameters{
        string(name: 'PERSON' defaultValue:'MR.Jenkins', description: 'say hello to this person')
        text(name: 'BIOGRAPHY' defaultValue: '', description: 'Enter info abt the person')
        // booleanParam(name: 'TOGGLE' defaultValue: true, description:'toggle this value')
        // string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        // text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('DEV') {
            steps {
              echo "Hello this is ${dev} Stage"
            }
        }
        
         stage('QA-testing') {
            steps {
              echo "Hello this is ${qa}-testing Stage"
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
              echo "Hello this is ${prod} Stage"
            }
        }
        stage('check params'){
            steps{
                sh """
                    echo "Hello ${params.PERSON}"

                    echo "Biography: ${params.BIOGRAPHY}"

                    echo "Toggle: ${params.TOGGLE}"

                    echo "Choice: ${params.CHOICE}"

                    echo "Password: ${params.PASSWORD}"
                """
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
