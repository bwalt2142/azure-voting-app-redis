pipeline {
   agent {label "docker-build"}

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Docker Build') {
         steps {
           sh 'docker images -a'
           sh 'cd azure-vote/'
           sh 'docker images -a'
           sh 'docker build -t jenkins-pipeline .'
           sh 'docker images -a'
           sh 'cd ..'                        
         }
      }
   }
}