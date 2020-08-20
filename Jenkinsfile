pipeline {
    agent { label 'local_host' }
	stages {
	   stage('checkout') {
	     steps {
		   git 'git@github.com:bibekanandmohanty/spring-petclinic.git'
		 }
	   }
	   stage('install') {
	     steps {
		   sh 'ansible-playbook tomcat.yml'
		 }
           }
	}

}
