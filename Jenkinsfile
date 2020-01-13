pipeline {
    agent any

    environment {
        DOCKER_USERNAME = "yaimer"
        DOCKER_PASSWORD = "123456789"
        DOCKER_REGISTRY = "yamier/zookeeper"
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
                            chown jenkins: /var/run/docker.sock
                            BUILD_VERSION_NUMBER=0.1.1
                            docker build -t mytest_docker .
                            docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
                            docker tag mytest_docker:latest $DOCKER_REGISTRY/mytest_docker:$BUILD_VERSION_NUMBER
                            docker push $DOCKER_REGISTRY/mytest_docker:$BUILD_VERSION_NUMBER
                            chown root: /var/run/docker.sock
                            '''
                        }
            }
            }
    }
