pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh "mvn clean package"    
            }
        }
        stage("Deploy"){
            steps{
                deploy adapters: [tomcat7(credentialsId: '6f457b58-24d2-428e-8841-24727baeea28', 
                                          path: '', 
                                          url: 'http://ec2-18-130-111-144.eu-west-2.compute.amazonaws.com:8080')], 
                    contextPath: 'javawebapp', 
                    war: '**/java-web-project.war'   
            } 
        }
    }
}
