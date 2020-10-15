pipeline {
    agent {
        label "tomcat"
    }
    environment {
        // This can be nexus3 or nexus2
        NEXUS_VERSION = "nexus3"
        // This can be http or https
        NEXUS_PROTOCOL = "http"
        // Where your Nexus is running
        NEXUS_URL = "162.243.164.195:8081"
        // Repository where we will upload the artifact
        NEXUS_REPOSITORY = "CI"
        // Jenkins credential id to authenticate to Nexus OSS
        NEXUS_CREDENTIAL_ID = "nexus"
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
