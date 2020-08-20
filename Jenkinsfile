Frontend Jenkins Pipeline

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
        sh 'npm test'
      }
    }
    stage('Package') {
      steps {
        sh ' npm run package'
      }
    }
    stage ('Archival'){
      steps {
        echo 'Archiving'
        archiveArtifacts '**/distribution/*.zip'
      }


    }
    }//stages
 }//pipeline

