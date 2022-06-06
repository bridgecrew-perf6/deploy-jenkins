pipeline {
   agent any
   stages {

        stage('deploy_dev'){
            when {
                branch 'homologacao'
            }

            dir("/opt/docker-sistemas/deploy-jenkins/")
              
            steps{
                sh """
                cd /opt/docker-sistemas/deploy-jenkins/
                """
            }
        }	

   }

}