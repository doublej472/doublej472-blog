
pipeline {
       agent any

       stages {
              stage('Prepare') {
                     steps {
                            sh '''
                            if [ ! -f $JENKINS_HOME/bin/blogc ]; then
                                   mkdir -vp $JENKINS_HOME/bin
                                   curl -sL https://github.com/blogc/blogc/releases/download/v0.20.1/blogc-static-amd64-0.20.1.xz | xz -d > $JENKINS_HOME/bin
                                   chmod +x $JENKINS_HOME/bin/blogc
                            fi
                            '''
                     }
              }
              stage('Build') {
                     steps {
                            sh 'make BLOGC=$JENKINS_HOME/bin/blogc all'
                     }
              }
              stage('Deploy') {
                     steps {
                            echo 'TODO'
                     }
              }
       }

}
