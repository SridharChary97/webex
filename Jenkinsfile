node{
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '7', daysToKeepStr: '', numToKeepStr: '7')), pipelineTriggers([cron('* * * * *')])])
        
def mavenHome = tool name: "Maven3.8.4"

stage('git'){
        git credentialsId: '1213aae3-f3a5-481e-b290-5acda81e8945', url: 'https://github.com/SridharChary97/webex.git'
    }
stage('mavenbuild'){
    sh "${mavenHome}/bin/mvn clean package"
}    

/* stage('deploytotom'){
    sshagent(['5b362484-a2f5-4241-9647-9a9168f9a491']) {
        sh "scp -o StrictHostKeyChecking=no target/webappExample.war ec2-user@3.14.130.234://opt/apache-tomcat-9.0.58/webapps"
}
} */
    
}
