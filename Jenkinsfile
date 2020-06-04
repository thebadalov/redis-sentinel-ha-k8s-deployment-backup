pipeline {
  agent none
  stages {
    stage('Service node'){
    agent any
    steps{
        sh "kubectl apply -f /var/lib/jenkins/workspace/redis-ha-deploy/create-service.yaml"
      }
    }
    stage('Master node'){
    agent any
    steps{
      sh "kubectl apply -f /var/lib/jenkins/workspace/redis-ha-deploy/create-master-deployment.yaml"
    }
  }
    stage('Sentinal node'){
    agent any
    steps{
      sh "kubectl apply -f /var/lib/jenkins/workspace/redis-ha-deploy/create-sentinel-deployment.yaml"
    }
  }
    stage('Slave node'){
    agent any
    steps{
      sh "kubectl apply -f /var/lib/jenkins/workspace/redis-ha-deploy/create-slave-deployment.yaml"
    }
  }
 }
}
