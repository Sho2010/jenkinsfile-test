#!groovy
node {
    stage "hello jenkins"
    echo "Work　Jenkinsfile!!"

    stage "file check out"    
    git 'https://github.com/sho2010/jenkinsfile-test'
    
    stage "docker build"
    def tag = "test-nginx:${env.BRANCH_NAME}-${env.BUILD_NUMBER}"
    def myContainer = docker.build "${tag}"
}
