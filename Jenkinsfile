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
            docker images -a
            cd azure-vote/
            docker images -a
            docker build -t jenkins-pipeline .
            docker images -a
            cd ..            
         }
      }
   }
}