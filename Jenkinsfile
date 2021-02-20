pipeline {
  agent {
    docker {
      image "node:8-alpine" 
    }
  }
  stages {
    stage("Build"){
      steps {
        sh  "apt-get install mongodb"
        sh  "chmod +x ./scripts/dropdb.sh"
        sh  "npm install"
      }
    }
    stage("Test") {
      steps {
        sh  "npm run test:ci"
      }
    }
  }
}
