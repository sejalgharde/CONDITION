pipeline {
	agent any
	
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/sejal/Documents/devops-software/apache-maven-3.9.5/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			script {
			 if ( env.ENVIRONMENT == 'QA' ){
        	sh 'cp target/CONDITION.war /home/sejal/Documents/devops-software/apache-tomcat-9.0.82/webapps'
			 }
			elif ( env.ENVIRONMENT == 'UAT' ){
    		sh 'cp target/CONDITION.war /home/sejal/Documents/devops-software/apache-tomcat-9.0.82/webapps'
			}
			fi
			
			}}}	
}}
