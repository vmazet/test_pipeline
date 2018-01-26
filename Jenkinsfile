#!groovy

node('node') {


    currentBuild.result = "SUCCESS"

    //try {

	  
		stage('Build') {
			echo 'Building..'
	    }
	           
	    stage('Test') {
	              
	     	echo 'Testing..'
	               
	    }
		
	    stage('Deploy') {
	         
	        echo 'Deploying....'
	               
	    }


    /*}
    *catch (err) {
	*
    *    currentBuild.result = "FAILURE"
	*	echo 'FAILURE'
    *    throw err
    *}
	*/
}
