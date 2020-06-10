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
	   }
	 }
     stage("Run Test")
	 {
	   steps 
	   {
	     bat "docker-compose up --scale chrome=5 search-module find-module"
	   }
	 }
   }
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			bat "docker-compose down"
		}
	}
   
}
