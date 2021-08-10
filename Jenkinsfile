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
     
                steps {
    withSonarQubeEnv('SonarCloud') {
        echo '''$SCANNER_HOME/bin/sonar-scanner -Dsonar.organization=$ORGANIZATION \	
        -Dsonar.projectKey=$PROJECT_NAME \
        -Dsonar.sources=./cidr_convert_api \
    }
  }
}
            
    }
}
