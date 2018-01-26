#!groovy

node('node') {


    currentBuild.result = "SUCCESS"

    try {

	   stages {
	   

			   stage ('phileas - Checkout') {
			 	   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], url: 'https://github.com/vmazet/test_pipeline.git']]]) 
		       }
	   
	           stage('Build') {
	               steps {
	                   echo 'Building..'
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
    catch (err) {

        currentBuild.result = "FAILURE"
		echo 'FAILURE'
        throw err
    }

}
