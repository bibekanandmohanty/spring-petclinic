pipeline {
    agent {
        label "tomcat"
    }
    stages {
        stage("clone code") {
            steps {
                script {
                    // Let's clone the source
                    git 'https://github.com/bibekanandmohanty/spring-petclinic.git';
                }
            }
        }
        stage("mvn build") {
	       agent { label 'tomcat'}
            steps {
                sh 'mvn clean compile'
        	}
       }
       
    }
}
