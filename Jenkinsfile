pipeline {
  agent any
  stages {
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
        withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
          sh '''
            echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
            docker push preethidevi/student-app:latest
          '''
        }  
      }
    }
  }
}

