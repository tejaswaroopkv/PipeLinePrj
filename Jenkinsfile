pipeline {
    agent any 
        parameters {
            string(name:  'Environment', defaultValue:  'PROD')
    }'


    stages {
        stage('build') {
            steps {
                parallel (
                    hw: {
                            bat 'javac HelloWorld.java'
                            bat 'java HelloWorld'
                        },
                    hw1: {
                            bat 'javac HelloWorld1.java'
                            bat 'java HelloWorld1'
                        }
                ) // end of block parallel
               } // end of block steps
           } // end of block stage
       } // end of block stages
    post {
    always {
        build 'example'
    }
}

    } // end of block pipeline
