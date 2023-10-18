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
		
          stage('Deploy on Application Machine') {
	      steps {
		  sh "nohup java -jar target/spring-boot-maven-jib-example-0.9.jar &"
		}
	}		
    }
}
