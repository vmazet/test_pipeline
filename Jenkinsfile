pipeline {
    agent any
	def container

    stages {
        stage('Build') {
            steps {
			    sh """ 
			    cd $WORKSPACE/apptest;
				npm install; 
				npm run build;
			    cd ..;
			    docker build -t demo.veltys.com/pipeline_test:latest .;
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
    }
}