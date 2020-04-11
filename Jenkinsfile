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
		    bat "echo HI"
			//bat "mvn install -Dbrowser=chrome -Dheadless=false"
        }
      } 
	  stage('Deploy') {
	    steps {
		    bat "echo HI"
	        //archiveArtifacts 'target/*.jar'
	    }
      }
	  stage('Notification') {
	    steps {
			emailext ()
	    }
	  }
	}
}