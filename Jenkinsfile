pipeline {
  agent any

  tools {
    maven 'Maven'  // Must match the name configured in Jenkins
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'master', url: 'https://github.com/saniya-gs/mavenfinal.git'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Run Application') {
      steps {
        sh 'java -jar target/*.jar'
      }
    }
  }

  post {
    success {
      echo 'Pipeline completed successfully!'
    }
    failure {
      echo 'Pipeline failed!'
    }
  }
}
