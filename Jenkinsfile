pipeline {
  agent any
  stages {
    stage('Git Checkout') {
      steps {
        git branch: 'master', url: 'https://github.com/Reddie77/star-agile-health-care.git'
                        }
            }
  stage('Create Package') {
      steps {
        echo 'This stage will compile, test, package my application'
        sh 'mvn package'
                          }
            }
    stage('Create Docker Image') {
      steps {
        echo 'This stage will Create a Docker image'
        sh 'docker build -t reddie777/healthcare:1.0 .'
                          }
            }
     stage('Docker-Login') {
           steps {
              withCredentials([usernamePassword(credentialsId: 'dockercreds', passwordVariable: 'dockerpassword', usernameVariable: 'dockerlogin')]) {
               sh 'docker login -u ${dockerlogin} -p ${dockerpassword}'
                             
                        }
                }
}
    stage('Docker Push-Image') {
      steps {
        echo 'This stage will push my new image to the dockerhub'
        sh 'docker push reddie777/healthcare:1.0'
            }
      }
  }
}
