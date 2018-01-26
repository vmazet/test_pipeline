pipeline {

    stages {
        stage('Build') {
			steps {
			
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
