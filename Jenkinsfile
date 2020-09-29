pipeline{
    agent any
    stages {
        stage('Checkout') {
            steps{
                    docker bulid -t harbor.test.101nd.cn/dangogo/my-nginx:v2 .
                    docker login -u 111203 -p Daneil147 harbor.test.101nd.cn
                    docker push harbor.test.101nd.cn/dangogo/my-nginx:v2
                    echo '---This is a Checkout step---'                 
            }
        }
        stage('Build') {
            steps{
            echo '---This is a Build step---'
            }
        }
        stage('Run') {
            steps{
                    echo '---This is a run step---'    
            }
        }
    }
}
