pipeline {
  agent none
  stages {
    stage('Compile') {
      agent {
        docker {
          image 'schoolofdevops/node:4-alpine'
        }

      }
      steps {
        echo 'Compilation'
        sh 'npm install'
      }
    }

    stage('Validate') {
      agent {
        docker {
          image 'schoolofdevops/node:4-alpine'
        }

      }
      steps {
        sh '''npm install 
npm test'''
      }
    }

    stage('Package') {
      agent {
        docker {
          image 'schoolofdevops/node:4-alpine'
        }

      }
      steps {
        sh '''npm install 
npm run package'''
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts '**/*.zp'
      }
    }

  }
}