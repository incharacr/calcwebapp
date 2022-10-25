pipeline{
    agent any
    tools{
        maven 'maven3.8.6'
        
    }
    
    stages{
       stage('GetCode'){
            steps{
                git 'https://github.com/incharacr/calcwebapp.git'
            }
        }        
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
       stage('Deploy'){
            steps{
                script{
                    deploy adapters: [tomcat8(credentialsId: 'Deployer', path: '', url: 'http://43.205.138.159:8080/')], contextPath: '/calcapp', onFailure: false, war: '**/*.war'
                    
                }
            }
        }
        
       
    }
}
    
        
        
           
