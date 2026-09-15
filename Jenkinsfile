pipeline {
    agent any

    tools {
        maven 'LocalMaven'
    }

    stages {

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }
        stage('Archive Artifact') {
     	    steps {
                archiveArtifacts artifacts: 'target/*.jar'
    	    }
   	    }
    }

    post {
        success {
            echo 'Build Successful'
        }

        failure {
            echo 'Build Failed'
        }
    }
}
