pipeline {
   agent any

   parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Qual é o seu nome?')
   }

   environment{
        MY_FILE = fileExists '/opt/docker-sistemas/deploy-jenkins/sistema/vendor'
    }

   stages {
       stage('clean ws'){
           steps{
               cleanWs()
           }
       }

       stage('deploy_dev'){
            steps{
                dir("/opt/docker-sistemas/deploy-jenkins"){
                    git branch: 'homologacao', url: 'https://github.com/kevinfelipe/deploy-jenkins.git'
                }

                echo "Olá ${params.PERSON}"
            }

            /*steps{
                sh """
                cd /opt/docker-sistemas/deploy-jenkins/
                composer install
                """
            }*/
        }	

        stage('Composer'){
            input {
                message "Você quer usar o composer ?"
                ok "Executar"
                parameters {
                    choice(name: 'COMPOSER', choices: ["Nenhum", "Install", "Update"], description: 'Executar Composer?')
                }
            }
            steps {
                script{
                    echo "Concatenar composer: " + params.COMPOSER
                    echo "Concatenar PERSON: " + params.PERSON
                    if (params.COMPOSER == "Install") {
                        echo 'Composer Install'
                    } else if (params.COMPOSER == "Update") {
                        echo 'Composer Update'
                    } else {
                        echo 'Nenhuma escolha'
                    }


                    if (MY_FILE == 'true'){
                        echo 'existe'
                    } else {
                        echo 'nao existe'
                    }
                }

                
            }
        }

   }

}