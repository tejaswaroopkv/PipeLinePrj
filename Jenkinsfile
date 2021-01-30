pipeline {
    agent any 
        parameters {[
                     booleanParam(name:  'Environment', defaultValue:  true , description: 'Environment should be true') ,
                     booleanParam(defaultValue: true,description: 'isBar should be true',name: 'isBar')
                   ]}
        
        
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
           stage('ParamUsage') {
            steps {
                echo "DEBUG: parameter Environment =  ${params.Environment}"
                echo 'DEBUG: parameter Environment =' + params.Environment
                 print 'DEBUG: parameter isFoo = ' + params.isBar
                echo env.path
            }
        }
       } // end of block stages
    post {
    always {
            build 'example'
        }
    }
} // end of block pipeline
