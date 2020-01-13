pipeline {
    agent any

    environment {
        DOCKER_USERNAME = "yaimer"
        DOCKER_PASSWORD = "123456789"
        DOCKER_REGISTRY = "yamier"
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
                            sh '''
                            BUILD_VERSION_NUMBER=0.1.1ß
                            docker build -t zookeepper .
                            docker login -u 'yamier' -p '123456789'
                            docker tag zookeepper:latest $DOCKER_REGISTRY/zookeepper:$BUILD_VERSION_NUMBER
                            docker push $DOCKER_REGISTRY/zookeepper:$BUILD_VERSION_NUMBER
                            '''
                        }
            }
            }
    }
