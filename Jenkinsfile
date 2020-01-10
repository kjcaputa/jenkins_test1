pipeline {
    agent any

    stages {
            stage('build') {
                steps {
                    sh './gradlew clean build'
                }
            }

            stage('push-image') {
                        steps {
                            sh './gradlew docker'
                            }
                        }
            }
    }
