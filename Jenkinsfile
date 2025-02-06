pipeline {
  agent any
     
  tools {
    maven 'maven' // Name must match the Maven installation in Jenkins Global Tool Configuration
  }

  stages {
    stage('Verify Java Version') {
      steps {
        sh '''
          env | grep -e PATH -e JAVA_HOME
          which java
          java -version
          mvn -v
        '''
      }
    }

    stage('Scan') {
      steps {
        withSonarQubeEnv(credentialsId: 'sonarqube-sever-token-ID', installationName: 'SonarQube_Server') {
          sh "mvn clean verify sonar:sonar -Dsonar.projectKey=conjur-credentials -Dsonar.projectName='conjur-credentials'"
        }
      }
    }
  }
}
