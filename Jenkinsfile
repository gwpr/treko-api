pipeline {
  agent {
    docker  {
      image "node:edge-alpine"
      args "--network=skynet"
    }
  }
  stages {
    stage("Build") {
      steps {
         sh "apk add mongodb"
         sh "mongo --version"
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
