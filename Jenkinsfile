pipeline {
    agent any

    stages {

       stage ('Docker Hub Login')
       {
          steps {
            withCredentials([usernamePassword(credentialsId: 'my-credentials', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')])
            {
               sh 'echo $PASSWORD'
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