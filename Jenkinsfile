pipeline {
    agent any
    stages {
        
        stage("Checkout") {
            
            steps {
                git branch: dev , url: https://github.com/lokeshvallepu/RxJava.git
            }
            
        }
        stage("Build") {
            
            steps {
                sh "mvn clean compile"
            }
        }
        
        stage("Test") {
            
            steps {
                
                sh "mvn test"
            }
            
        }

        stage("package") {
            steps {
                
                sh "mvn package"
                
            }            
        }

        stage ("Dockerize app") {

            steps {
                sh "docker buil -t lokeshvallepu/rxjapp:1.0.1"
                
            }
        }
        
    }
}
