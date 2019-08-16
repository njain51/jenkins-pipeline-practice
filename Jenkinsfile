pipeline {
  agent {
    docker {
      image 'maven:3.3.9-jdk-8'
    }

  }
  stages {
    stage('Checkout') {
      steps {
        echo 'Initialize Stage'
      }
    }
    stage('Build') {
      steps {
        echo 'Build Stage'
        sh '''echo PATH = ${PATH}
echo M2_HOME = ${M3}
mvn clean compile'''
      }
    }
    stage('Test') {
      steps {
        echo 'Testing Stage'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        echo 'Package Step'
        sh 'mvn package'
      }
    }
  }
  environment {
    label = 'linux'
  }
}