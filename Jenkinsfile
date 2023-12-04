pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        sh '${MVN_HOME}/bin/mvn clean package'
      }
    }
    stage ('SonarQube Analyses') {
     steps {
          withSonarQubeEnv('sonar6') {
            sh '${MVN_HOME}/bin/mvn sonar:sonar'
          }
     }
    }
  }
}
