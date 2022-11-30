
pipeline {
       agent any

       stages {
              stage('Build') {
                     steps {
                            sh 'make all'
                     }
              }
              stage('Deploy') {
                     steps {
                            sshagent(credentials: ['blogdeploy']) {
                            sh '''
                                   [ -d ~/.ssh ] || mkdir ~/.ssh && chmod 0700 ~/.ssh
                                   ssh-keyscan static.doublej472.com >> ~/.ssh/known_hosts
                            '''
                            }

                            sh 'rsync -Rpv --delete-after _build/ blogdeploy@static.doublej472.com:/data/blog/'
                     }
              }
       }

}
