pipeline {
  agent {
    docker  {
      image "node:8-alpine"
    }
  }
  stages {
    stage("Build") {
      step  {
         sh "npm install"
      }
    }
  }
}
