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
	 stage("Bring Grid Down")
	 {
	   steps
	   {
	     bat "docker-compose down"
	   }
	 }
   }
   
}
