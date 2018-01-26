#!groovy

node('node') {


    currentBuild.result = "SUCCESS"

    try {

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
    catch (err) {

        currentBuild.result = "FAILURE"
		echo 'FAILURE'
        throw err
    }

}
