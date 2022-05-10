node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      } 
      environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub-cred-raja')
	}

      stage('Build image') {         
       
            app = docker.build("1818181818/test-18")    
       }              
      stage('Push image') {
docker.withRegistry('https://registry.hub.docker.com', 'git') {            
       app.push("${env.BUILD_NUMBER}")            
       app.push("latest")        
              }    
           }
        }
