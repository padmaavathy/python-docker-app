node{
   stage("App Build started"){
      echo 'App build started..'
      git 'https://github.com/padmaavathy/python-docker-app.git'
      }
      
    stage("Docker Build"){
     def app = docker.build "manee2k6/padmavathy"
     }
    
    stage("Tag & Push image"){
       docker.withRegistry([credentialsId: 'DockerID', url: 'https://hub.docker.com']){
       //withDockerRegistry([credentialsId: 'DockerID', url: 'https://hub.docker.com']) {
       app.push()
      }
    }
    
    stage("App deployed"){
     echo 'App deployed to Hub..'
    }


}
