pipeline {
    agent any

    tools {
        maven 'mvn_home'
    }

    stages {

        stage('SCM-Checkout') {
            steps {
                checkout scmGit(
                    branches: [[name: '*/main']],
                    extensions: [],
                    userRemoteConfigs: [[
                        credentialsId: 'github-pat',
                        url: 'https://github.com/TejasG30/my-app.git'
                    ]]
                )
            }
        }

        stage('Maven Clean') {
            steps {
                sh 'mvn clean'
            }
        }

        stage('Maven Build') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('Maven Deploy') {
            steps {
                sh 'mvn package'
            }
        }
    }


}
