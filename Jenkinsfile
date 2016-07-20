#!groovy
node {
    stage "hello jenkins"
    echo "Work　Jenkinsfile!!"
    sh 'gcloud auth list'

    stage "file check out"    
    checkout scm
    
    stage "docker build"
    def tag = "test-nginx:${env.BRANCH_NAME}-${env.BUILD_NUMBER}"
    def myContainer = docker.build "${tag}"
}
