pipeline {
    agent {
    label 'aws-agent'
    }


    stages {
        stage('build') {
            steps {
               sh 'mvn clean package'
            }
        }

        stage('test') {
            steps {
                echo "test in progress"
            }
        }

        stage('deploy') {
            steps {
                echo "deploy in progress"
            }
        }
    }

     post {
      success {
        slackSend channel: 'jenkins', message: '"Build Success  - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"', teamDomain: 'Jenkins-Training', tokenCredentialId: 'slack-notfications'
      }
      failure {
       slackSend channel: 'jenkins', message: '"Build failed  - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"', teamDomain: 'Jenkins-Training', tokenCredentialId: 'slack-notfications'
      }
    }
    
}
