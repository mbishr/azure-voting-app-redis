pipeline {
   agent any

   stages {
      stage('Checkout') {
         steps {
            git 'https://github.com/mbishr/azure-voting-app-redis.git'
         }
      }
      stage('Docker Build') {
         steps {
            sh(script: 'docker images -a')
            sh(script: """
               cd azure-vote/
               docker images -a
               docker build -t jenkins-pipeline .
               docker images -a
               cd ..
            """)
         }
      }
   }
}