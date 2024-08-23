pipeline {
   agent any

   stages {
      stage('Docker Hub Login')
       {
         steps {
            withCredentials([usernamePassword(credentialsId: 'dockerhub_id', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')])
            {
               sh 'docker login -u $USERNAME -p $PASSWORD'
            }
         }
       }

      stage('Build')
       {
         agent {
            docker {
               image 'node:18-alpine'
            }
         }

         steps {
            sh '''
                 touch ali.txt
                 node --version >> ali.txt
            '''
         }
       }

      stage('Create Nginx')
        {
            steps {
            sh '''
                  docker pull nginx:latest
                  docker run -d --name nginx -p 80:80 nginx
                  '''
            sh 'cp ali.txt $WORKSPACE/ali.txt'
            }
        }
   }
   post {
      always {
         sh 'cat $WORKSPACE/ali.txt || true'
      }
   }
}
