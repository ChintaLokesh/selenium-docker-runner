pipeline
{
   agent any 
   stages
   {
     stage("Start the Grid")
	 {
	   steps
	   {
	     bat "docker-compose up -d hub chrome firefox --scale chrome=5"
	   }
	 }
     stage("Run Test")
	 {
	   steps 
	   {
	      bat "docker-compose up testng.xml testng1.xml"
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
