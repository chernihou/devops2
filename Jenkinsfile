pepeline{
  agent any 
  tools {
    maven 'maven'
  }
  stages {
    stage ("Clean up"){
      steps {
        deleteDir()
      }
    }
    stage ("Clone repo"){
      steps {
        sh "https://github.com/chernihou/devops2.git"
      }
    }
    stage ("Generate backend image"){
      steps{
        dir("devops2"){
          sh "mvn clean install"
          sh "docker build -t devops2 ."
        }
      }
    }
    stage ("Run docker compose"){
      steps { 
        dir("devops2"){
        sh "docker compose up -d"
      }}}}}
