pipeline {
  agent {
    kubernetes {
      yamlFile 'agent.yaml'
    }
  }
  stages {
    stage('Docker Build') {
      steps {
	    container('sonar') {
	      git 'https://gitlab.com/dexterrorez/dosch.git'
          checkout scm
          sh "sonar-scanner   -Dsonar.projectKey=epam-cicd-school-16   -Dsonar.sources=."
	    }
      }
    }
  }
}