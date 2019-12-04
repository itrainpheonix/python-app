node{
   
   stage(" Code Checkout"){
      echo 'App build started..'
      git credentialsId: 'githubID', url: 'https://github.com/itrainpheonix/python-app.git'
      }
   stage('Code Build') {
     echo 'App build started..'
    }
   stage('Unit Test') {
     echo 'App test started..'
    }
   stage('Code Analysis') {
     echo 'App analysis started..'
    }
   
   stage('Docker Build') {
     def app = docker.build "manee2k6/itrain-pheonix-pyapp"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'github-docker',url: ""]) {
          sh 'docker tag manee2k6/itrain-pheonix-pyapp manee2k6/itrain-pheonix-pyapp:dev'
          sh 'docker push manee2k6/itrain-pheonix-pyapp:dev'
          sh 'docker push manee2k6/itrain-pheonix-pyapp:latest'
      }
    }
    stage("App deployment started"){
     //sh 'oc login --token=t01XSPheqChA1n1QxmPCSJAwm5rFNYzb7FvRP9mmg6A --server=https://api.us-east-1.online-starter.openshift.com:6443'
          // sh 'oc new-project creativetech'
      
    // sh 'oc new-app shiddu/pythonimage:dev --name python --env NEWRELIC_LICENSE=xxxxxx NEWRELIC_APPNAME=pyapp'
    // sh 'oc expose svc python --name=python'
    // sh 'oc status'
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   


   
























}
