pipeline{
			agent{
					label 'built-in'
					customWorkspace '/data/project/game-of-life'
			}
			stages{
					
			
					stage ('game-of-life-home'){
							
							steps {
							         sh "rm -rf /root/.m2/repository"
							
							}
					
					stage ('game-of-life'){
							
							steps {
							         sh "mvn clean install"
							
							}
							}
					stage ('path'){
							
							steps {
							
								sh "cp -r /data/project/game-of-life/gameoflife-web/target/gameoflife.war /mnt/tomcat/apache-tomcat-9.0.65/webapps"
							
							}
					
					}
					
					}
			
			
			}


}
