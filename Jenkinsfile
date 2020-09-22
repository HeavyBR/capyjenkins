pipeline {
  agent {
    docker {
        image 'qaninja/rubywd'
    }
  }

  stages {
    stage('Build') {
        steps {
            echo 'Building or Resolving dependencies!'
            sh 'rm -f Gemfile.lock'
            sh 'bundle install'
        }
    }
    stage('Test') {
        steps {
            echo 'Running regression tests'
            sh 'bundle exec cucumber -p ci'
            cucumber failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: -1, fileIncludePattern: '**/*.json', jsonReportDirectory: 'logs', pendingStepsNumber: -1, skippedStepsNumber: -1, sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1
        }
    }
  }
}
