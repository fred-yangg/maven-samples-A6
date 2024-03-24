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

    stage('git bisect') {
      steps {
        sh '''git bisect start 198644632661c67b6c32f59e9047c11a70685e15 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5
git bisect run mvn clean test'''
      }
    }

  }
  tools {
    maven 'Automatic Maven'
    jdk 'OpenJDK 11'
  }
}