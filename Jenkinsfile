pipeline {
    agent any

    stages {

       stage ('Docker Hub Login')
       {
          steps {
            withCredentials([usernamePassword(credentialsId: "dockerhub_id", usernameVariable: "USERNAME", passwordVariable: "PASSWORD")])
            {
               sh 'echo $PASSWORD | docker login -u $USERNAME --password-stdin'
            }
          }
       }

      //  stage ('Build')
      //  {
      //    agent {
      //       docker {
      //            image 'node:18-alpine'
      //       }
      //    }

      //    steps {

      //       sh ''' 
      //            touch test.txt
      //            echo "Hello From Docker in Docker " >> test.txt
      //       '''
      //    }
      //  }

      //  stage ('Create Nginx')
      //  {
      //      steps {
               
      //      }
      //  }

      //  post {
      //     always {
               
      //          sh ``` 
      //               cat test.txt
      //          ```
      //     }
      //  }

    }
}