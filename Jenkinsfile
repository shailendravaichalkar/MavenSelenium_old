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
			emailext (
				subject: "Job is '${env.JOB_NAME} ${env.BUILD_NUMBER}'",
				body: """<p>Check console output at <a href="${env.BUILD_URL}">${env.JOB_NAME}</a></p>""",
				to: "vaichalkar.shailendra@gmail.com",
				from: "vaichalkar.shailendra@gmail.com"
			)
	    }
	  }
	}
}