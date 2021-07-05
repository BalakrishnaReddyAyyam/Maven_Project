#!groovy

node{
stage("codecheckout")
{
git credentialsId: 'b863abf3-a198-4877-9206-443cdd14f3e8', url: 'https://github.com/BalakrishnaReddyAyyam/Maven_Project.git'
}
stage("maven")
{
def mvnHOME = tool name: 'linuxmaven', type: 'maven'
sh "${mvnHOME}/bin/mvn clean deploy"
}
stage("tomcat")
{
sh 'cp /home/ec2-user/.jenkins/workspace/MyFirstPipelineJob/target/*.war /home/ec2-user/apache-tomcat-10.0.7/webapps/'
}
}
