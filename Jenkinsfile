pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("Deploy"){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'a170da00-3a00-464f-ae37-9fb8c3fb7ca0', path: '', url: 'http://ec2-52-27-222-210.us-west-2.compute.amazonaws.com:8080')], 
                contextPath: 'javawebapp', 
                war: '**/java-web-project.war'
            }
        }
    }
}
