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
      stage('Login') {

		steps {
			sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}
      stage('Push image') {
docker.withRegistry('https://registry.hub.docker.com', 'git') {            
       app.push("${env.BUILD_NUMBER}")            
       app.push("latest")        
              }    
           }
        }
