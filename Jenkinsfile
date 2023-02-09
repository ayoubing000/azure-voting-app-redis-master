pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Docker Build') {
         steps {
            sh(script: 'docker images -a')
            sh(script: """
               cd azure-vote/
               sudo sudo docker images -a
               sudo docker build -t jenkins-pipeline .
               sudo docker images -a
               cd ..
            """)
         }
      }
   }
}
