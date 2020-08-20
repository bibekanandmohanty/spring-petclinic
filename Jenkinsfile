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
        stages {
           stage('checkout') {
             agent {
                label 'deploy'
             }
             steps {
                   git 'git@github.com:bibekanandmohanty/spring-petclinic.git'
                 }
           }
           stage('Build') {
             agent {
                label 'deploy'
             }
             steps {
                   sh 'mvn clean compile'
                 }
           }
           stage('test') {
             agent {
                label 'deploy'
             }
             steps {
                   sh 'mvn test'
                   junit '**/target/surefire-reports/*.xml'
                 }
           }
           stage('Package') {
             agent {
                label 'deploy'
             }
             steps {
                   sh 'mvn package'
                 }
           }
        }



}
