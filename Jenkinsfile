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
               args '-v $WORKSPACE:/workspace'
            }
         }

         steps {
            sh '''
                 touch /workspace/ali.txt
                 node --version >> /workspace/ali.txt
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
            }
        }
   }
   post {
      always {
         echo "I can't make the file access globale in all stages"
      }
   }
}
