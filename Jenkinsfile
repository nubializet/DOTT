pipeline {
        agent any
             stages {
                 stage('Checkout-git'){
                      steps {
                       git poll: true, url: 'https://github.com/nubializet/DOTT'    
                      }
                 }   
                 stage('Build') {
                      steps {
                        sh "docker image build . -t /cidr_convert_api/ruby"
                       }
                 }
                stage('Sonarqube') {
                      environment {
                        SCANNER_HOME = tool 'SonarQubeScanner'
                        SONAR_TOKEN = "7db027d86418fb4e6cec9e9fa98e4c98423557ce"
                        ORGANIZATION = "nubializet-github"
                        PROJECT_NAME = "nubializet-DOTT"
                      }
                      steps {
                        withSonarQubeEnv('SonarCloud')  {
                            sh """$SCANNER_HOME/bin/sonar-scanner --version\
                            -Dsonar.organization=$ORGANIZATION \
                            -Dsonar.projectKey=$PROJECT_NAME \
                            -Dsonar.sources=./cidr_convert_api/ruby """
                        }
                      }
                    }
                    
                    stage('Testing') {
                        steps {
                               echo 'Testing' 
                        }
                    }
                    stage('Deploy') {
                        steps {
                        echo 'Deploying'
                            }
                     }
                     
    }
}
