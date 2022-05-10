node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      } 
      environment {
		DOCKERHUB_CREDENTIALS=credentials('test-18')
	}

      stage('Build image') {         
       
            app = docker.build("1818181818/test-18")    
       }     
      
      stage('Push image') {
docker.withRegistry('https://registry.hub.docker.com', 'test-18') {            
       app.push("${env.BUILD_NUMBER}")            
       app.push("latest")        
              }    
           }
        }
