pipeline {
  agent none
 tool {
 node = 'node486'	
} 
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
        archiveArtifacts '**/*.zip'
      }
    }

  }
}
