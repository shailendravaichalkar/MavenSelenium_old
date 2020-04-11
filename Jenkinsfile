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
			//bat "mvn install -Dbrowser=chrome -Dheadless=false"
        }
      } 
	  stage('Deploy') {
	    steps {
	        //archiveArtifacts 'target/*.jar'
	    }
      }
	  stage('Notification') {
	    steps {
	        emailext body: 'This is automated mail from Jenkins. $DEFAULT_CONTENT', 
			subject: 'JENKINS: (${JOB_NAME}) (${BUILD_NUMBER}) : $DEFAULT_SUBJECT', 
			to: 'vaichalkar.shailendra@gmail.com'
	    }
	  }
	}
}