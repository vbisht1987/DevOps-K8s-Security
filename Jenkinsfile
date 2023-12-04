pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        sh '${M2_HOME}/bin/mvn clean package'
      }
    }
    stage ('SonarQube Analyses') {
     steps {
          withSonarQubeEnv('sonar6') {
            sh '${M2_HOME}/bin/mvn sonar:sonar'
          }
     }
    }
  }
}
