pipeline{
    agent any
    stages {
        stage('Checkout') {
            steps{
            git credentialsId: '85ca7e47-532e-4901-9828-50a8da071d16', url: 'http://xxx.gitlab.com/webapplication_jenkinsfile.git', branch:'master'
                    echo '---This is a Checkout step---'                 
            }
        }
        stage('Build') {
            steps{
                    sh '''cd WebApplication_Jenkinsfile
            docker rmi -f docker_webapplication_test:1.0
            docker build -t docker_webapplication_test:1.0 .'''
            echo '---This is a Build step---'
            }
        }
        stage('Run') {
            steps{
            sh '''docker rm -f docker_webapplication_test
            docker run --name docker_webapplication_test -d -p 7489:80 docker_webapplication_test:1.0
            '''
                    echo '---This is a run step---'    
            }
        }
    }
}
