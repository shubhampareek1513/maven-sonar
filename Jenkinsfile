pipeline{
agent any 
stages{
stage('scm checkout')
{

steps{
           git branch: 'master', url: 'https://github.com/shubhampareek1513/maven-sonar.git'

}}

stage('sonar and maven package')
{
steps{

withSonarQubeEnv(credentialsId: 'mysonar') {
    withMaven(jdk: 'localjdk', maven: 'local-mvn') {
    sh 'clean mvn install sonar:sonar'
}
}
}
}
}
}
