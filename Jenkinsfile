pipeline {
  agent {
    docker {
      image 'nginx'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''# step 1
echo build'''
      }
    }
    stage('Test') {
      steps {
        sh '''# step 2
echo step2'''
      }
    }
    stage('Deploy') {
      steps {
        archiveArtifacts 'README.md'
      }
    }
  }
  post {
    always {
      archiveArtifacts(artifacts: 'README.md', fingerprint: true)

    }

  }
}