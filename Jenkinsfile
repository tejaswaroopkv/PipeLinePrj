pipeline {
    agent any 
    stages {
        stage('build') {
            steps {
                parallel {
                    hw: {
                            bat 'javac HelloWorld.java'
                            bat 'java HelloWorld'
                        },
                    hw1: {
                            bat 'javac HelloWorld.java'
                            bat 'java HelloWorld'
                        }
                   } // end of block parallel
               } // end of block steps
           } // end of block stage
       } // end of block stages
    } // end of block pipeline
