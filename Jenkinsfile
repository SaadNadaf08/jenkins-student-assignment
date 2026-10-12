
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Compiling application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests... Pass!'
            }
        }

        stage('Package') {
            steps {
                script {
                    def buildInfo = "Build Number: ${env.BUILD_NUMBER}\nBuild Timestamp: ${new Date()}\n"
                    writeFile file: 'build-info.txt', text: buildInfo
                }
                echo 'Created build-info.txt'
            }
        }
    }

    post {
        success {
            echo 'Build successful! Ready for release.'
        }
    }
}
