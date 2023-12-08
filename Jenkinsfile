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
            sh 'mvn sonar:sonar -Dsonar.host.url=http://192.168.29.109:8094'
          }
     }
    }
  }
}
