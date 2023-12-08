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
            sh 'mvn sonar:sonar -Dsonar.host.url=http://192.168.29.109:8094 -Dsonar.login=147B411E-AYw0K5rsPYGLB3IYxVND'
          }
     }
    }
  }
}
