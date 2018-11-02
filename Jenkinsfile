node{

stage('Code pull')
{
git 'https://github.com/Mayank2905/web.git'
}
stage('build through maven')
{
sh 'mvn package'
}
stage('deploy to remote server')
  {
    sshagent(['deploy-server']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.35.199:/opt/tomcat7/webapps'
}
  }
}
