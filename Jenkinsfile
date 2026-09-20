pipeline{
    agent{ label'Jenkins-Agent'}
    tools {
        jdk 'Java17'
        maven 'Maven1'        
    }
    stages{
        stage("cleanup workspace"){
                steps{
                cleanWs()
                }
        }
       
        stage("checkout from SCM"){
                steps {
                git branch:'main', credentialsId: 'github', url: 'https://github.com/pushpender19945-web/Register-App'
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
