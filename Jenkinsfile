pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        echo 'Checkout Stage'
        tool(name: 'M3', type: 'maven')
      }
    }
    stage('Build') {
      steps {
        echo 'Build Stage'
        sh '''echo PATH = ${PATH}
echo M2_HOME = ${M2_HOME}
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