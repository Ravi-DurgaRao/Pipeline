pipeline {
    agent any
    stages {
        stage('Init') {
            steps {
                echo 'Initializing..'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
        stage('Test1') {
            steps {
                echo 'Testing..'
                echo 'Running pytest..'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                echo 'Running docker build -t sntshk/cotu .'
            }
        }
        stage('Publish') {
            steps {
                echo 'Publishing..'
                echo 'Running docker push..'
            }
        }
        stage('Cleanup') {
            steps {
                echo 'Cleaning..'
                echo 'Running docker rmi..'
            }
        }
        stage('Test') {
            steps {
                script {
                    def passTest = true
                    def failTest = false

                    if (passTest) {
                        echo 'Test Case 1: Passed'
                    } else {
                        error 'Test Case 1: Failed'
                    }

                    /*if (failTest) {
                        echo 'Test Case 2: Passed'
                    } else {
                        error 'Test Case 2: Failed'
                    }*/
                }
            }
        }
    }
    /*post {
        always {
            echo 'Pipeline completed.'
        }
    }*/
}
