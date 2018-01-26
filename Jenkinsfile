pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
				checkout scm
			    sh """ 
			    cd $WORKSPACE/apptest;npm install; npm run build;
			    """
            }
        }
        stage('Test') {
            steps {
			    withSonarQubeEnv {
			        sh "./gradlew clean sonarqube"
			    }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}