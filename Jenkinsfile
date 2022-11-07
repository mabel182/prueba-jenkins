def JOB_NAME = env.JOB_NAME
def BUILD_ID= env.BUILD_ID
    
pipeline {
    agent any
            
    stages {
        stage('Build') {
            steps {
                slackSend failOnError: true, message: "Build Started: ${env.JOB_NAME} ${env.BUILD_NUMBER}"
                echo 'TODO: build'
                sh './mvnw clean compile -e'
            }
        }
        stage('Test') {
            steps {
                echo 'TODO: test'
                sh './mvnw clean test -e'
            }
        }
        stage('Package') {
            steps {
                echo 'TODO: package'
                sh './mvnw clean package -e'           
            }
        }
        stage('Run') {
            steps {
                echo 'TODO: run'
                sh 'nohup bash ./mvnw spring-boot:run &'                      
            }           
        }
        stage('Clean Workspace') {
            steps {     
                cleanWs()
                slackSend channel: '#builds', color: 'good', message: 'Finish job'
            }           
        }
    }
}
