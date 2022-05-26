pipeline {

    agent {

        label "master"
    }

    tools {

        maven "MAVEN"
    }

    
    stages {
        stage('Build Maven') {
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GithubLove', url: 'https://github.com/oredebi/jenkins-maven.git']]])

                sh "mvn -Dmaven.test.failure.ignore=true clean package"
                
            }
        }
    }
    
}
