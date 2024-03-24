pipeline {
  agent any
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/fred-yangg/maven-samples.git', branch: 'master')
      }
    }

    stage('clean') {
      steps {
        sh 'mvn clean'
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('verify') {
      steps {
        sh 'mvn verify'
      }
    }
  }
  tools {
    maven 'Automatic Maven'
    jdk 'OpenJDK 11'
  }
}
