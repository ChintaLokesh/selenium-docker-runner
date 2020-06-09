pipeline
{
   agent any 
   stages
   {
     stage("Start the Grid")
	 {
	   steps
	   {
	     bat "docker-compose up -d hub chrome"
	     bat "docker-compose scale chrome=5"
	   }
	 }
     stage("Run Test")
	 {
	   steps 
	   {
	     bat "docker-compose up search-module find-module"
	   }
	 }
	}
     post {
        always {
            archiveArtifacts artifacts: 'output/**'
            bat "docker-compose down"
        }
    }	
}
