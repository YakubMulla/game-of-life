pipeline {
    agent {
        label {
            label '172.31.0.97'
            customWorkspace '/mnt/project/'
        }
    }
    stages{
        stage ('repo-clone-1'){
            steps {
                sh "rm -rf *"
                sh "git clone https://github.com/YakubMulla/game-of-life.git"
                sh "rm -rf /root/.m2/repository"
            }
        }
        stage ('mvn-build-1'){
            steps {
                dir('/mnt/project/game-of-life/'){
                    sh "mvn clean install"
                }
            }
        }
        stage ('deployment on Slave-1'){
            steps {
                sh "cp -r /mnt/project/game-of-life/gameoflife-web/target/gameoflife.war /mnt/tomcat/apache-tomcat-9.0.65/webapps/"
            }
        }

    stage ('repo-clone-2'){
 agent {
        label {
            label '172.31.11.39'
            customWorkspace '/mnt/project/'
        }
 }
 
            steps {
                sh "rm -rf *"
                sh "git clone https://github.com/tejasshete244/game-of-life.git"
                sh "rm -rf /root/.m2/repository"
            }
    }
        
        stage ('mvn-build-2'){
             agent {
        label {
            label '172.31.11.39'
        }
 }
            steps {
                dir('/mnt/project/game-of-life/'){
                    sh 'mvn clean install'
                }
            }
        }    
        stage ('deployment on Slave-2'){
             agent {
        label {
            label '172.31.11.39'
        }
 }
            steps {
                dir('/mnt/tomcat/apache-tomcat-9.0.67/webapps/'){
                    sh "cp -r /mnt/project/game-of-life/gameoflife-web/target/gameoflife.war /mnt/tomcat/apache-tomcat-9.0.67/webapps/"
                }
            }
          }
   }
}
