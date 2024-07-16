pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                // Clone of the repos
                git https://github.com/kennytoro/jenkins101.git
            }
        }

        stage('Build') {
            steps {
                // Building stage
                sh '''
                echo "This is the building stage with a build number of ${BUILD_ID}"
                echo 'Built successfully'
                '''
                echo " The Build Url is ${BUILD_URL}"
            }
        }

        stage('Deploy') {
            steps {
                // This is the deploy stage 
                sh '''
                ls
                df -h
                lsblk
                '''
                echo " kubectl apply -f ."
                echo " Deployment of the pod done"
            }
        }

        stage('Test') {
            steps {
                echo " It is working"
            }
        }
    }

    post {
        sucess {
            // Actions to be perform when the pipeline is successful
            echo " T for Thanks... Man go job on ${BUILD_ID} build"
        }
        failure {
            echo "Pipeline failed... Ooops man down"
        }
    }
}