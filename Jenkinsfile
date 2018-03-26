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
          sh 'docker tag manee2k6/padmavathy manee2k6/padmavathy:001'
          sh 'docker push manee2k6/padmavathy:latest'
          sh 'docker push manee2k6/padmavathy:001'
      }
    }
    
    stage("App deployed"){
     echo 'App deployed to Hub..'
    }


}
