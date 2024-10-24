/*
pipeline {
    agent any
 
    stages {
        stage('build') {
            steps {
                echo 'Building image , hey jude. Dont make it bad. Take a sad song and make it better.'
            }
        }
       stage('testing') {
            steps {
                echo 'testing....HEY JUDEEEEE'
            }
        }
        stage('deploy') {
            steps {
                echo 'No Deployment for now. Sorry!!'
            }
        }
    }
}
*/

pipeline {
   agent any

   tools {
   go 'go' // The installed go binary name on the server
   }
   environment {
       DOCKER_IMAGE = 'hello-go'
   }


   stages{
       stage('Run Docker Build'){
           steps{
               script{
                    echo "starting docker build"
                    sh "docker build . -t hello-go:latest"
                    echo "docker built successfully"
               }
           }
       }
       stage('push to docker hub'){
           steps{
               echo "===No docker hub push for now==="
            //    script{
            //        docker.withRegistry('https://index.docker.io/v1/', 'dockerhub'){
            //            docker.image("${DOCKER_IMAGE}:${env.BUILD_ID}").push()
            //        }
            //    }
               echo "done"
           }
       }
   }


   post {
       always{
           cleanWs()
       }
   }
}