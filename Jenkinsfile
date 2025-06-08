pipeline {
  agent any

  tools {
    maven 'Maven'
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
        sh 'java -jar target/MavenApp-1.0-SNAPSHOT.jar'
      }
    }
  }
}
      
