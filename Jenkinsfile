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
                     
                stage('Sonarqube - sonarcloud'){
                    steps{
                        script { env.SONAR_TOKEN="7db027d86418fb4e6cec9e9fa98e4c98423557ce" }
                        dir("cidr_convert_api/ruby/convert.rb"){
                            echo 'result'}
                    }   
         }             
    }
}
