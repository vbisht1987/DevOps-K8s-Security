pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        sh '${MVN_HOME}mvn clean package'
      }
    }
    stage ('SonarQube Analyses') {
     steps {
          withSonarQubeEnv('sonar6') {
            sh '${mvnHome}/bin/mvn sonar:sonar'
          }
     }
    }
  }
}
