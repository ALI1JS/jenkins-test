pipeline {
    agent any

    stages {

       stage ('Docker Hub Login')
       {
          steps {
            withCredentials([usernamePassword(credentialsId: 'dockerhub_id', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')])
            {
               sh 'docker login -u $USERNAME -p $PASSWORD'
            }
          }
       }

       stage ('Build')
       {
         agent {
            docker {
                 image 'node:18-alpine'
            }
         }

         steps {

            sh ''' 
                 touch ali.txt
                 echo node --version >> ali.txt
            '''
         }
       }

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