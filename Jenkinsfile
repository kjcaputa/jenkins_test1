pipeline {
    agent any


    stages {
            stage('build') {
                steps {
                    sh 'chmod +x gradlew'
                    sh './gradlew clean build'
                }
            }

            stage('push-image') {
                        steps {
                            sh '''
                            BUILD_VERSION_NUMBER=V1.0.0
                            docker build -t zookeeper .
                            docker login -u 'yamier' -p '123456789'
                            docker tag zookeeper:latest yamier/zookeeper:$BUILD_VERSION_NUMBER
                            docker push yamier/zookeeper:$BUILD_VERSION_NUMBER
                            '''
                        }
            }
            }
    }
