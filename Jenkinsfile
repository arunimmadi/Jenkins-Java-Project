pipeline {
  agent any
  
  options {
    buildDiscarder(logRotator(numToKeepStr: '2', artifactNumToKeepStr: '1' ))
  }
stages {
  stage ('Unit Testing') {
    steps {
      sh 'ant -f test.xml -v'
      junit 'reports/result.xml'
    }
  }
  stage ('Build') {
  steps {
   echo "Building"
   }
 }
 stage ('test') {
 steps {
  echo "Testing"
   }
 }
 stage ('Deploy') {
 steps {
   echo "Deploying"
      }
    }
  stage ('Build_number') {
  steps {
    echo "My Branch Name: ${env.BRANCH_NAME}"
   }
  post {
    always {
      archiveArtifacts artifacts: 'dist/', fingerprint: true
      }
    }
  }
}
}
