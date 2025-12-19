pipeline {

    agent {
        label 'agent-aws'
    }

    stages {

        stage('build') {
            steps {
                script {
                    sh 'docker build -t java-app .'
                }
            }
        }

        stage('push') {
            steps {
                script {
                    withCredentials([usernamePassword(
                        credentialsId: 'docker-hub',
                        passwordVariable: 'Password',
                        usernameVariable: 'Username'
                    )]) {

                        sh 'docker login --username $Username --password $Password'
                        sh 'docker tag java-app $Username/java-app'
                        sh 'docker push $Username/java-app'
                    }
                }
            }
        }

        stage('deploy') {
            steps {
                script {
                    
                        sh 'kubectl apply -f ./k8s/deployment.yaml'
                    }
                }
            }
        }

    }

