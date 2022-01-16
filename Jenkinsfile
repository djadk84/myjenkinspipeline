pipeline {
  agent any
  tools {
   maven 'M3'
   }
  stages { 
    stage('Checkout') {
      steps {
        git 'https://github.com/djadk84/myjenkinspipeline.git'
        }
    }
    stage('build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage ('Package') {
      steps {
        sh 'mvn package'
        }
      }
 }
}