pipeline {
  agent any
	tools {
		jdk "JAVA_HOME"
		maven "MAVEN_HOME"
	}
  stages {
  	stage('Build') {
	  steps {
	  sh 'mvn clean package'
	  deploy adapters: [tomcat8(credentialsId: 'admin', path: '', url: 'http://localhost:8010')], contextPath: null, war: 'target/JenkinsWar.war'
	  }
  	}
  }
}
