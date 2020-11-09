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
                always {
                mail to: 'hiteshkumawat7878@gmail.com',
                subject: "Failed Pipeline:",
                emailext attachLog: true,
                body: "Something is wrong with code pull or may be conflicts occur."
                }
        }
}
