pipeline {
    agent any

    stages {
        stage('Build') {
			steps {
				withEnv(["JAVA_HOME=${ tool '"+JDK+"' }", "PATH=${env.JAVA_HOME}/bin"]) { 

					withMaven(jdk: '(Hérite du job)', maven: 'mvn') { 
			 			//if(isUnix()) {
			 				sh "mvn -f back clean install spring-boot:repackage " 
						//} else { 
			 			//	bat "mvn -f back clean install spring-boot:repackage " 
						//}
        			}
				}
			}	
		}		
		
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
