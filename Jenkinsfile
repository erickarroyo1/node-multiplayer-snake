node ('Ubuntu-app-agent'){  
    def app
    stage('Cloning Git') {
        /* Let's make sure we have the repository cloned to our workspace */
       checkout scm
    }
    stage('Build-and-Tag') {
    /* This builds the actual image; synonymous to
         * docker build on the command line */
        app = docker.build("amrit96/snake")
    }
   
     stage('Post-to-dockerhub') {

            registry = "191006/erick_public-repo:Snake_app"
         }
       
    stage('Pull-image-server') {
    
         sh "docker-compose down"
         sh "docker-compose up -d"	
     }
}

// a standalone single line comment here
