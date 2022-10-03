# ansible-config-mgt
save_artifact and jenkinsfiles
#### Quick Task Jenkinfile
pipeline {
    agent any

  stages {
    stage('Initial Cleanup') {
      steps {
        dir("${WORKSPACE}") {
          deleteDir()
        }
      }
    }
    stage('Build') {
      steps {
        script {
          sh 'echo "Building Stage"'
        }
      }
    }

    stage('Test') {
      steps {
        script {
          sh 'echo "Testing Stage"'
        }
      }
    }
    stage('Package') {
      steps {
        script {
          sh 'echo "Packaging App"'
        }
      }
    }
    stage('Deploy') {
      steps {
        script {
          sh 'echo "Deploying to Dev"'
        }
      }
    }
    stage('Clean Up') {
      steps {
        cleanWs()
      }
    }
  }
}

