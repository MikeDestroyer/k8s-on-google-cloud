pipeline {
    agent any
    tools {
        nodejs 'NodeJS 19.2.0'
    }
    stages {
//        stage('Git pull'){
//            steps {
//                git branch: 'main', credentialsId: 'git', url: 'git@github.com:MikeDestroyer/k8s-on-google-cloud.git'
//            }
//        }
        stage('ReactJS App test'){
            steps {
                dir('client') {
                    sh 'ls'
                    sh 'npm install'
                    sh 'npm run test --watchAll=false --ci --coverage'
                }

            }
        }
        stage('Build client container')
            agent {
                dockerfile {
                    filename 'Dockerfile.test'
                    dir 'client'
                }
            }
    }
}