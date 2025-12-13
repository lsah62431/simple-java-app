pipeline {
    agent any
    environment {
            JAVA_HOME = "/usr/lib/jvm/java-21-openjdk-amd64"
            MAVEN_HOME = "/usr/share/maven"
            PATH = "${JAVA_HOME}/bin:${MAVEN_HOME}/bin:${env.PATH}"
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



}
   
