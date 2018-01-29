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
		       
		      sh "mvn clean verify -Dtags='type:Smoke'"
		        
		   }
		   stage('API') {
		      steps {  
		      	sh "mvn clean verify -Dtags='type:API'"
		      }  
		   }
		   stage('UI') {
		      steps {
		     	 sh "mvn verify -Dtags='type:UI'"
		       } 
		   }
		   stage('Results') {
		   	  steps {
		      	junit '**/target/failsafe-reports/*.xml'
		   	  } 
		   }
    }
}