pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }        
        
        stage('Deploy to Tomcat server') {
            steps {
              deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tompass', path: '', url: 'http://3.84.164.227:8080/')], contextPath: 'myapp', war: '**/*.war'
            }
        }
    }
}
