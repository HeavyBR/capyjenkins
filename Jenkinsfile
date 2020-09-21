pipeline {
  agent {
    docker {
        image 'ruby'
    }
  }

  stages {
    stage('Build') {
        steps {
            echo 'Building or Resolving dependencies!'
            sh 'bundle install'
        }
    }
    stage('Test') {
        steps {
            echo 'Running regression tests'
        }
    }
  }
}
