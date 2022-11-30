
pipeline {
       agent any

       stages {
              stage('Prepare') {
                     steps {
                            sh '''
                            if [ ! -f ./blogc ]; then
                                   curl -sL https://github.com/blogc/blogc/releases/download/v0.20.1/blogc-static-amd64-0.20.1.xz | xz -d > ./blogc
                                   chmod +x ./blogc
                            fi
                            '''
                     }
              }
              stage('Build') {
                     steps {
                            sh 'make BLOGC=./blogc all'
                     }
              }
              stage('Deploy') {
                     steps {
                            echo 'TODO'
                     }
              }
       }

}
