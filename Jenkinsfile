node('master') 
{
    stage('ContinuousDownload_loans') 
    {
        git 'https://github.com/Pramodh003/maven.git'
    }
    stage('ContinuousBuild_loans') 
    {
        sh 'mvn package'
    }
    stage('ContinuousBuild_loans') 
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/pipelinetype1/webapp/target/webapp.war ubuntu@172.31.46.231:/var/lib/tomcat8/webapps/testenv.war'
    }
    stage('ContinuousBuild_loans') 
    {
        git 'https://github.com/Pramodh003/Functional-Testing.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/pipelinetype1/testing.jar'
    }
     stage('ContinuousDelivery_loans') 
    {
        input 'wait for approval of DM'
        sh 'scp /home/ubuntu/.jenkins/workspace/pipelinetype1/webapp/target/webapp.war ubuntu@172.31.33.149:/var/lib/tomcat8/webapps/prodenv.war'
    }
}
