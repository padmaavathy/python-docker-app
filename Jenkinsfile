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
          sh 'docker tag manee2k6/padmavathy manee2k6/padmavathy:002'
          sh 'docker push manee2k6/padmavathy:latest'
          sh 'docker push manee2k6/padmavathy:002'
      }
    }
   
   stage("App deployment started"){
     sh 'oc login https://api.starter-us-west-1.openshift.com --token=l334xAzzGBl7kvYuUFcvfRCCXMsQxeQJox3pEzbSQrQ'
     sh 'oc new project padmavathy'
     sh 'oc new-app manee2k6/python-app:pattabhi-1.0 --name python-app'
     sh 'oc expose svc python-app --name=python-app'
     sh 'oc status'
    }
    
    stage("App deployed"){
     echo 'App deployed to Hub..'
    }


}
