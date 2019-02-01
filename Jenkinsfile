pipeline {
  agent {
    node {
      label 'jenkins-slave'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'echo "build"'
      }
    }
    stage('Test') {
      steps {
        echo 'tests were successful'
      }
    }
  }
}