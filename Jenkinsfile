pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                sh 'mvn clean package'
            }
        }
        stage("Deploy") {
            steps {
                deploy adapters: [tomcat7(credentialsId: '102bc175-39e0-4887-9cf6-01c7c43a5d80', path: '',
                        url: 'http://ec2-54-175-161-148.compute-1.amazonaws.com:8080/')],
                        contextPath: 'javawebapp', war: '**/javawebproject.war'
            }
        }
    }
}
