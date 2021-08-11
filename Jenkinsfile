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
                stage('testing, for sonarcloud'){
            steps{
                script { env.SONAR_TOKEN="823c288ab7a9a14f75cd2597c417ec3eef8602a2" }


            }   
        }
                     
                     
                     
    }
}
