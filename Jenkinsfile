pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh """
				cd $WORKSPACE/apptest;npm install; npm run build;
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