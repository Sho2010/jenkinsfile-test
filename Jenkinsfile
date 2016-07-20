#!groovy
node ('gcloud'){
    stage "hello jenkins"
    echo "Work　Jenkinsfile!!"

    stage "file check out"    
    checkout scm
    
    stage "docker build"
    // env.GCP_PROJECT is jenkins global enviroment 
    def tag = "gcr.io/${env.GCP_PROJECT}/test-nginx:${env.BRANCH_NAME}-${env.BUILD_NUMBER}"
    def myContainer = docker.build "${tag}"
    
    stage 'docker push to gcr.io'
    sh('gcloud docker -a')
    myContainer.push()
}
