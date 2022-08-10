pipeline {
   agent none
   stages {
      stage("build & SonarQube analysis") {
        agent any
        environment {
	       scannerHome = tool 'SonarQube Scanner'
	     }
        steps {
            withSonarQubeEnv('admin') {
               sh "mvn clean verify sonar:sonar -Dsonar.projectKey=java"
            }
        }
      }
   }
}
