node('master')
{
    stage('ContinuousDownload') 
    {
       git 'https://github.com/intelliqittrainings/maven.git'
    }
    stage('ContinuousBuild')
    {
        sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/sPipeline/webapp/target/webapp.war ubuntu@172.31.39.30:/var/lib/tomcat8/webapps/testapp.war'
    }
    stage('ContinuousTesting')
    {
        git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
        sh label: '', script: 'echo "Testing Passed"'
    }
    stage('ContinuousDelivery')
    {
         sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/sPipeline/webapp/target/webapp.war ubuntu@172.31.34.76:/var/lib/tomcat8/webapps/prodapp.war'
    }
    
    
    
}

