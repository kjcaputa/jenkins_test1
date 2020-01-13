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
                            BUILD_VERSION_NUMBER=V1.0
                            DOCKER_REGISTRY = yamier
                            docker build -t zookeepper .
                            docker login -u 'yamier' -p '123456789'
                            docker tag zookeepper:latest $DOCKER_REGISTRY/zookeepper:$BUILD_VERSION_NUMBER
                            docker push $DOCKER_REGISTRY/zookeepper:$BUILD_VERSION_NUMBER
                            '''
                        }
            }
            }
    }
