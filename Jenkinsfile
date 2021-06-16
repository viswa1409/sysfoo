pipeline {
  agent {
    docker {
      image 'maven:3.6.3-jdk-11-slim'
    }

  }
  stages {
    stage('build') {
      steps {
        echo 'compile sysfoo app'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'test sysfoo app'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'package sysfoo app'
        sh 'mvn package -DskipTests'
      }
    }

    stage('artifact') {
      steps {
        archiveArtifacts 'target/*war'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
}