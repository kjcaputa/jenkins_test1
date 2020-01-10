pipeline {
    agent {
        dockerfile true
        }
    }

    stages {
            stage('build') {
                steps {
                    sh 'chmod +x gradlew'
                    sh './gradlew clean build'
                }
            }

            stage('push-image') {
                        steps {
                            sh './gradlew docker -i -s'
                            }
                        }
            }
    }
