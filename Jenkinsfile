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

        stage('Dependency Installation') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-practice .'
            }
        }

        stage('Run Docker Image') {
            steps {
                sh "docker run -d -p 3001:3000 jenkins-practice"
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


