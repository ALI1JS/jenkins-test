pipline {
    agent any

    stages {

       stage ('Docker Hub Login')
       {
          steps {
            withCredentials([usernamePassword(credentialsId: "alijs", usernameVariable: "USERNAME", passwordVariable: "PASSWORD")])
            {
               sh ''' 
                  docker login -u $USERNAME -p $PASSWORD
               '''
            }
          }
       }

    }
}