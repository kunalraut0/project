pipeline {
    agent any 
    stages {
        stage('pull') { 
            steps {
                git 'https://github.com/kunalraut0/project.git'
            }
        }
        
        stage('build') { 
            steps {
               sh 'mvn clean install'
            }
        } 
        
        stage('test') { 
            steps {
                echo 'test successful'
            }
        }
        
        stage('deploy') { 
            steps {
               deploy adapters: [tomcat9(credentialsId: '24858404-37d8-43d0-8593-4a2a2461eef6', path: '', url: 'http://3.110.174.84:8081/')], contextPath: '/', war: '**/*.war'
            }
        } 
    }
}    
