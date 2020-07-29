pipeline {
  agent {
    docker  {
      image "node:8-alpine"
    }
  }
  stages {
    stage("Build") {
      steps {
         sh "apk add mongodb=3.4.4-r0 mongo --version"
         sh "chmod +x ./scripts/dropdb.sh"
         sh "npm install"
      }
    }
    stage("Test") {
      steps {
       sh "npm run test:ci"
      }
    }
}
}
