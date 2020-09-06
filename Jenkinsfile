@Library('pipeline-library-demo')_

stage('Demo') {

  echo 'Hello World'

  sayHello 'Nitin'

}

pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build Stage now'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing Stage'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploy Stage'
      }
    }
  }
}