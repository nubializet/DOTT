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
                        echo 'bundle install'
                             }
                 }
                     
    }
}
