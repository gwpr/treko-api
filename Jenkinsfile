pipeline {
  agent {
    docker  {
      image: "node:8-alpine"
    }
  }
  stages {
    stage("Build") {
      sh "npm install"
    }
  }
}
