pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                sh 'git clone https://github.com/AbdullahDaniyal/simple-reactjs-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t lab-11:1 ."
            }
        }

        stage('Run Docker Image') {
            steps {
                sh 'docker run -d -p 80:80 lab-11'
            }
        }

        // stage('Push Docker Image') {
        //     steps {
        //         script {
        //             docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
        //                 docker.image(env.DOCKER_IMAGE).push('latest')
        //             }
        //         }
        //     }
        // }
    }

    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
    }
}
12:49 pm


