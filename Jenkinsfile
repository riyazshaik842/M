node ('master')
{
    stage ('continuous download')
    {
    
        git 'https://github.com/riyazshaik842/M.git'
    }
    
    stage ('continuous build')
    {
        sh 'mvn package'
    }
    
    stage ('continuous deployment')
    {
        sh 'scp /var/lib/jenkins/workspace/pipeline/webapp/target/webapp.war ubuntu@172.31.24.3:/var/lib/tomcat7/webapps/qaenv.war'

    }
    
    stage ('continuous testing')
    {
        git 'https://github.com/riyazshaik842/Test.git'
        
        sh ''' java -jar /var/lib/jenkins/workspace/pipeline/testing.jar
'''
        
        
    }
    
    stage('continuous delivery')
    {
        input 'can we proceed with delivery?'
        
        sh '''scp /var/lib/jenkins/workspace/pipeline/webapp/target/webapp.war ubuntu@172.31.24.48:/var/lib/tomcat7/webapps/prodenv.war
'''
        
        
    }
    
    
    
    
    
}
    
    
    
    
    
    
    
    
    
    
    



}
