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
           stage('checkout1') {
               agent { 
                   label 'deploy'
            }
             steps {
                   git 'https://github.com/bibekanandmohanty/spring-petclinic.git'
                 }
           }
	}

}
