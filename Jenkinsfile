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
]		    dir('dosch'){
          sh "sonar-scanner   -Dsonar.projectKey=cicd-school   -Dsonar.sources=."
		    }
	    }
      }
    }
  }
}
