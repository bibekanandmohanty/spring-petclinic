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
    agent { label 'deploy' }
        stages {
           stage('checkout') {
             steps {
                   git 'git@github.com:bibekanandmohanty/spring-petclinic.git'
                 }
           }
           stage('Build') {
             steps {
                   sh 'mvn clean compile'
                 }
           }
           stage('test') {
             steps {
                   sh 'mvn test'
                   junit '**/target/surefire-reports/*.xml'
                 }
           }
           stage('Package') {
             steps {
                   sh 'mvn package'
                 }
           }
        }


}
