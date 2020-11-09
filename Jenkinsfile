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
                        emailext attachLog: true,
                                body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}",
                                subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}",
                                to: "hiteshkumawat7878@gmail.com"
                                
                }
        }
}
