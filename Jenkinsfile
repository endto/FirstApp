pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('parallel3') {
          steps {
            sh '''# step 1
echo build'''
          }
        }
        stage('parallel2') {
          steps {
            sh 'echo \'parallel\''
            sh 'echo "parallel2_1"'
          }
        }
      }
    }
    stage('Test') {
      steps {
        sh '''# step 2
echo step2'''
      }
    }
  }
  environment {
    label = 'jenksin-qa_e2e'
  }
  post {
    always {
      archiveArtifacts(artifacts: 'README.md', fingerprint: true)

    }

  }
}