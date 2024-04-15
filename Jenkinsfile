pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
            script {
                sh '''
                if [ ! -d "newDirectory" ]; then
                    git clone https://github.com/AbdullahDaniyal/simple-reactjs-app newDirectory
                fi
                '''
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                
                    sh 'npm install'
                
            }
        }

        stage('Build Docker Image') {
            steps {
                //sh "docker build -t lab-11:1 ."
                echo "sleep 2"
            }
        }

        stage('Run Docker Image') {
            steps {
                //sh 'docker run -d -p 80:80 lab-11'
                echo "sleep 1"
            }
        }

        stage('Push Docker Image') {
             steps {
                 script {
                     docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                         //echo "docker.image(env.DOCKER_IMAGE).push('latest')
                         echo "sleep 2"
                     }
                }
             }
         }
    }
}


