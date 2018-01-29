pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
			    sh """ 
			    cd $WORKSPACE/apptest;
				npm install; 
				npm run build;
			    cd ..;
			    """
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
		
		stage('Smoke') {
		     steps {
			 	git 'https://github.com/BushnevYuri/e2e-automation-pipeline.git'
			 	withMaven(jdk: '(Hérite du job)'){
					sh "mvn clean verify -Dtags='type:Smoke';"
				}
		     }   
		   }
		   stage('API') {
		      steps {  
			 	withMaven(jdk: '(Hérite du job)'){
					sh "mvn clean verify -Dtags='type:API';"
				}
		      }  
		   }
		   stage('UI') {
		      steps {
			 	withMaven(jdk: '(Hérite du job)'){
					sh "mvn clean verify -Dtags='type:UI';"
				}
		       } 
		   }
		   stage('Results') {
		   	  steps {
		      	junit '**/target/failsafe-reports/*.xml'
		   	  } 
		   }
    }
}