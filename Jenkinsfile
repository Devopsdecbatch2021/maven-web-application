node{
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
    
    
    
def mavenHome = tool name: "maven3.8.4"
stage('checkoutcode')
{
git branch: 'development', credentialsId: '2541d990-13c8-4af8-b072-208ccca890ca', url: 'https://github.com/Devopsdecbatch2021/maven-web-application.git'
}
stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
}
    /*
stage('execute sonarQube Report')
{
    sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage('uploadArtifactory into NexusRepo')
{
    sh "${mavenHome}/bin/mvn deploy"
}
stage('Deploy Application into Tomcat server')
{
    sshagent(['d0697c6c-ca7e-4e22-8846-395218ef17c3']) {

sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@65.0.124.32:/opt/apache-tomcat-9.0.58/webapps/"
}
}
*/
}
