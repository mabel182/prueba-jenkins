pipeline {
    agent any
            
    stages {
        stage('Build') {
            steps {
                slackSend channel: '#builds', color: 'good', message: 'Start job'
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
            }           
        }
    }
}
