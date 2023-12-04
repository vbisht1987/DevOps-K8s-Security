pipeline {
  agent any
  stages {
    stage ('SonarQube Analyses') {
     steps {
          withSonarQubeEnv('sonar6') {
            sh 'mvn sonar:sonar'
          }
     }
    }
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
  }
}
