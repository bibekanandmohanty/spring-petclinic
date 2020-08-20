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
           stage('checkout') {
               agent { 
                   label 'deploy'
            }
             steps {
                   git 'git@github.com:bibekanandmohanty/spring-petclinic.git'
                 }
           }
	}

}
