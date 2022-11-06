pipeline {
    agent any
            
    stages {
        slackSend channel: '#builds', color: '#439FE0', message: 'Start job'
        stage('Build') {
            steps {
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
