pipeline {
   agent any
   tools ('Init') {
      maven "localMaven"
    }
   stages {
      stage('Build') {
		steps {
			git 'https://github.com/shailendravaichalkar/MavenSelenium.git'
		}
      }
      stage('Test and Install') {           
        steps {
			bat "mvn install -Dbrowser=chrome -Dheadless=false"
        }
      } 
	  stage('Deploy') {
	    steps {
	        archiveArtifacts 'target/*.jar'
	    }
      }
	}
}
