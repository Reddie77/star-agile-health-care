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
  }
}
