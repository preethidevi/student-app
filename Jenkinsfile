pipeline {
  agent any
  stage {
    stage('clone') {
      steps {
        git 'https://github.com/preethidevi/student-app.git'
      }
    }
    stage('Build Image') {
      steps {
        sh 'docker build -t preethidevi/student-app:latest .'
      }
    }
    stage('Push Image') {
      steps {
          sh 'docker push preethidevi/student-app:latest'
         }
       } 
