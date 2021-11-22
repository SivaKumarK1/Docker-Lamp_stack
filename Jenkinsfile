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
                    sudo docker-compose up
                    '''
                    echo 'Docker is Up'
            }
        }
        stage('Finished'){
            steps{
                echo 'Build Successful !!'
            }
            post{
                success{
                    sh ''' brave http://localhost:5000 '''    
                }
            } 
        }
    }
}
