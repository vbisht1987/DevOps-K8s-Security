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
            sh 'mvn sonar:sonar -Dsonar.host.url=http://192.168.29.109:8094 -Dsonar.token=sqp_8c61b968b5660ba98426daf15769a814cc778c07'
          }
          timeout(time: 2, unit: 'MINUTES') {
              script {
                waitForQualityGate abortPipeline: true
              }
        }
     }
    }
  }
}
