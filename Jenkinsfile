pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        echo 'Compilation'
        sh 'npm install'
      }
    }

    stage('Validate') {
      steps {
        sh '''npm install 
             npm test'''
      }
    }

    stage('Package') {
      steps {
        sh '''npm install 
          npm run package'''
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts '**distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'node486'
  }
}