node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      } 
      environment {
		DOCKERHUB_CREDENTIALS=credentials('av21aman')
	}

      stage('Build image') {         
       
            app = docker.build("1818181818/test-18")    
       }     
      
      stage('Push image') {
docker.withRegistry('https://registry.hub.docker.com', 'av21aman') {            
       app.push("${env.BUILD_NUMBER}")            
       app.push("latest")        
              }    
           }
        }
