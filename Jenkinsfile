pipeline {
        agent {
      label 'agent-aws'
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
    slackSend channel: 'jenkins-slack', message: "Build Started - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'Jenkins-Training', tokenCredentialId: 'jenkins-slack'
  }
}


}
