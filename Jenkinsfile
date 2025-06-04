pipeline{
	agent any
	tools{
		maven 'Maven'
	}
	stages{
		stage('Checkout'){
			steps{
				git branch:'master',url:'https://github.com/nreddyg07/MJ.git'
			}
		}
		stage('Build'){
			steps{
				sh 'mvn clean package'
			}
		}
		stage('Test'){
			steps{
				sh 'mvn test'
			}
		}
		stage('Run Application'){
			steps{
				sh 'java -jar target/mavenjenkins-1.0-SNAPSHOT.jar'
			}
		}
	}
	post{
		success{
			echo 'Build and Deployment successful!'
		}
		failure{
			echo 'Build failed!'
		}
	}
}
