pipeline {
    // These are pre-build sections
    agent {
        node {
            label 'AGENT-1'
        }
    }
     environment {
         COURSE = "jenkins"

     }
    //  options {

    //     timeout(time: 10, unit: 'SECONDS')
    //     disableConcurrentBuilds()
    //  }
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {

        stage('Read Version') {
            steps {
                script {

                   def packageJSON = readJSON file: 'package.json'
                    appVersion = packageJSON.version
                    echo "app version: ${appVersion}"
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script{
                    sh """
                        npm install
                    """
                }
            }
        }

        stage('Build Image') {
            steps {
                script {
                   sh """
                   docker build -t catalogue:${appVersion} .
                   """
            }
        }
    }

 post{
        always{
            echo 'I will always say Hello again!'
            cleanWs()
        }

        success {
            echo 'I will run if success, we can write any code'

        }

        failure {
           echo 'I will run if failure, we can write any code'

        }
    
}       
}