pipeline{
    agent{ label'Jenkins-Agent'}
    tools {
        jdk 'java17'
        maven 'Maven3'        
    }
    stages{
        stage("cleanup workspace"){
                steps{
                cleanWs()
                }
        }
       
        stage("checkout from SCM"){
                steps {
                git brach:'main', credentialsId: 'github', url: 'https://github.com/pushpender19945-web/Register-App'
                }
        }

        stage("Build Application"){
                steps{
                sh "mvn clean package"
                }
        }

        stage("Test Application"){
                steps{
                sh "mvn test"
                }
        }
    }        
}    
