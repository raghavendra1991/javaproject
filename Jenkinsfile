pipeline {
   agent none
   stages {
      stage("build & SonarQube analysis") {
        agent any
        steps {
            withSonarQubeEnv('admin') {
               sh 'mvn clean test package sonar:sonar'
            }
        }
      }
   }
}
