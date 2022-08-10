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
               sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=java"
            }
        }
      }
   }
}
