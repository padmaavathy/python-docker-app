node{
   stage("App Build started"){
      echo 'App build started..'
      git 'https://github.com/padmaavathy/python-docker-app.git'
      }
      
    stage("Docker Build"){
     def app = docker.build "manee2k6/padmavathy"
     }
    
    stage("Tag & Push image"){
       withDockerRegistry([credentialsId: 'DockerID', url: 'https://hub.docker.com']) {
       sh 'docker push app'
      }
    }
    
    stage("App deployed"){
     echo 'App deployed to Hub..'
    }


}
