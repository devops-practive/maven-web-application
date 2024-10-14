node{
    
def mavenHome = tool name: "maven.3.8.6"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
    
stage('checkoutCode'){
git credentialsId: 'b2b4b906-76b0-4bb3-96c2-ccfb36a90370', url: 'https://github.com/devops-practive/maven-web-application.git'
}

stage('build'){
sh "${mavenHome}/bin/mvn clean package"
}
/*    
stage('uploadartifact'){
sh "${mavenHome}/bin/mvn clean deploy"
}

stage('DeploytoSrver'){
sshagent(['403759f3-c05f-4599-97eb-22b168f38a6d']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.12.14:/opt/apache-tomcat-9.0.96/webapps/"
}
}
*/
}
