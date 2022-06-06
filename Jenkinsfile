pipeline {
   agent any
   stages {

        stage('deploy_dev'){
            when {
                branch 'homologacao'
            }
              
            steps{
                sh """
                cd /opt/docker-sistemas/deploy-jenkins/
                composer install
                """
            }
        }	

   }

}