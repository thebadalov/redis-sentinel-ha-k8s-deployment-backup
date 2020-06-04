pipeline {
  agent none
  stages {
    stage('Service node'){
    agent any
    steps{
        sh "kubectl apply -f create-service.yaml"
      }
    }
    stage('Master node'){
    agent any
    steps{
      sh "kubectl apply -f create-master-deployment.yaml"
    }
  }
    stage('Sentinal node'){
    agent any
    steps{
      sh "kubectl apply -f create-sentinel-deployment.yaml"
    }
  }
    stage('Slave node'){
    agent any
    steps{
      sh "kubectl apply -f create-slave-deployment.yaml"
    }
  }
 }
}
