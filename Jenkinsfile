pipeline {
    agent { label 'jenkins-agent' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        }

        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'github', url: 'https://github.com/mohan0900/learning_git'
                }
        }

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

        }
		
        stage("Test Application"){
           steps {
                 sh "mvn test"
           } 
        }
    }
}
