pipeline {
    agent any

    stages {
        stage('SCM Checkout'){
            steps{
                git 'https://github.com/SivaKumarK1/Docker-Lamp_stack.git'
            }
        }
        stage('Build') {
            steps {
                sh '''
                    sudo docker-compose build
                    sudo docker-compose up -d
                    '''
                    echo 'Docker is Up'
            }
        }
        stage('push'){
            steps{
                sh '''
                    sudo docker login -u "shimigami" -p "Sammy@123@@" docker.io 
                    sudo docker push shimigami/lamp-stack:v1 
                '''
            }
        }
        stage('Finished'){
            steps{
                echo 'Build Successful !!'
            } 
        }
    }
}
