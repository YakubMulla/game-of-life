pipeline{
			agent {
				label {	
					label '172.31.0.97'
					customWorkspace '/data/project/game-of-life'
			          }
			      }
			stages{ 
			         stage ('install on slave-1'){
					agent {
							label {	
										label '172.31.0.97'
										customWorkspace '/data/project/game-of-life'
								  }
			              }
						  
						  steps {
	
							         sh "git clone https://github.com/YakubMulla/game-of-life.git"
							         sh "rm -rf /root/.m2/repository"
									 sh "mvn clean install"
									 sh "cp -r /data/project/game-of-life/gameoflife-web/target/gameoflife.war /mnt/tomcat/apache-tomcat-9.0.65/webapps"
							      }
					                            
			
					
							}
					stage ('install on slave-2'){
					agent {
							label {	
										label '172.31.11.39'
										customWorkspace '/data/project/game-of-life'
								  }
			              }
						  steps {
						  
							         sh "git clone https://github.com/YakubMulla/game-of-life.git"
									 sh "rm -rf /root/.m2/repository"
									 sh "mvn clean install"
									 sh "cp -r /data/project/game-of-life/gameoflife-web/target/gameoflife.war /mnt/tomcat/apache-tomcat-9.0.65/webapps"
									 
							
							      }
					                            
			
					
				  }
					}
					
					
					
					
						
					
					
			
			
			
}
