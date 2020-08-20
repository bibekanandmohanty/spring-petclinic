pipeline {
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
