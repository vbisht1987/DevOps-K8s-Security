pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('SonarQube Analyses') {
     steps {
          withSonarQubeEnv('sonar6') {
            sh 'mvn sonar6:sonar'
          }
     }
    }
  }
}
