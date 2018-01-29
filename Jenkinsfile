pipeline {
    agent any
	export JVM_ARGS="-Xms512m -Xmx1024m"
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
		
		stage('Performance Tests') {
			steps {
		    	parallel(
		        	BlazeMeterTest: {
		            	dir ('Taurus-Repo') {
		               	 	sh 'bzt $WORKSPACE/test.yml -report'
		            	}
		        	},
		        	Analysis: {
		            	sleep 60
		        	})
			}		
	   }
		
		stage('Smoke') {
		     steps {
			 	git 'https://github.com/BushnevYuri/e2e-automation-pipeline.git'
				withMaven(maven:'mvn'){
			 		sh "mvn clean verify -Dtags='type:Smoke'"
				}
		     }   
		   }
		   stage('API') {
		      steps {  
			 	withMaven(maven:'mvn'){
					sh "mvn clean verify -Dtags='type:API';"
				}
		      }  
		   }
		   stage('UI') {
		      steps {
			 	withMaven(maven:'mvn'){
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