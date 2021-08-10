pipeline {
        agent any
             stages {
                 stage('Checkout-git'){
                      steps {
                       git poll: true, url: 'https://github.com/nubializet/DOTT'    
                      }
                 }   
                 stage('build') {
                      steps {
                        echo 'gem install bundler'
                        echo 'bundle install'
                           }
                 }
                stage('SonarCloud') {
      environment {
        SCANNER_HOME = tool 'SonarQubeScanner'
        SONAR_TOKEN = credentials('SonarCloud')
        ORGANIZATION = "nubializet-github"
        PROJECT_NAME = "nubializet-DOTT"
      }
      steps {
        withSonarQubeEnv(installationName: 'SonarCloud', credentialsId: 'SonarCloud') {
            sh '''$SCANNER_HOME/bin/sonar-scanner -Dsonar.organization=$ORGANIZATION \
            -Dsonar.java.binaries=build/classes/java/ \
            -Dsonar.projectKey=$PROJECT_NAME \
            -Dsonar.sources=.'''
        }
      }
    }
    }
}
