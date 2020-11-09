pipeline {
        agent any
        parameters {
        	      string(defaultValue: "mypipeline", description: 'pulling branch', name: 'NAME')
        }
        stages {
                stage('running acript and testing') {
                   steps{
                        script {
                            sh '''
                                #!/bin/bash
                                echo `date`
                                echo $NAME
                                
                            '''
                        }
                   }
                }
        }
        post {
                Always {
                mail to: 'hkkumawat4466@gmail.com',
                subject: "Failed Pipeline:",
                body: "Something is wrong with code pull or may be conflicts occur."
                }
        }
}
