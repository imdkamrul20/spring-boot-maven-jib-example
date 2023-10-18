pipeline {
	agent any
    tools{
        maven 'maven3'
    }
    stages{   
        stage('Build') {
            steps {
                sh 'mvn clean package' // Assuming you are using Maven for building the microservices
            }
        }

		stages {
			stage('Deploy on Application Machine') {
				steps {
					#withCredentials([sshUserPrivateKey(credentialsId: 'your-credentials-id', keyFileVariable: 'KEY')]) {
						#sh "scp -i $KEY /target/spring-boot-maven-jib-example.jar user@your-deployment-machine:/path/to/destination"
						#sh "ssh -i $KEY user@your-application-machine 'nohup java -jar /path/to/your-service.jar &'"
						sh "nohup java -jar /target/spring-boot-maven-jib-example.jar  &"
					#}
				}
			}
		}

    }
}
