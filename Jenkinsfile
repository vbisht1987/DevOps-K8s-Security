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
          def mvnHome = tool name: 'maven', type: 'maven'
          withSonarQubeEnv('sonar6') {
            sh '${mvnHome}/bin/mvn sonar:sonar'
          }
     }
    }
  }
}
