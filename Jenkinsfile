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
	      git url:'https://gitlab.com/dexterrorez/dosch.git', branch: 'main'
          checkout scm
          sh "sonar-scanner   -Dsonar.projectKey=cicd-school   -Dsonar.sources=."
	    }
      }
    }
  }
}
