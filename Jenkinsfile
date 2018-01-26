pipeline {
    agent any

    stages {
        stage('Build') {
			steps {
				//withEnv() { 

					//withMaven(jdk: '(Hérite du job)', maven: 'mvn') { 
			 			//if(isUnix()) {
			 			//	sh "mvn clean package -DskipTests" 
						//} else { 
			 			//	bat "mvn -f back clean install spring-boot:repackage " 
						//}
        			//}
				//}
				
				sh """ 
				cd $WORKSPACE/apptest;npm install; npm run build;cd ..;
				 ""
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
