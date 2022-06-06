pipeline {
   agent any
   stages {

        stage('deploy_dev'){
            when {
                branch 'homologacao'
            }            
              
            steps{
                dir("/opt/docker-sistemas/deploy-jenkins"){
                     sh "pwd"
                }

            }
        }	

   }

}