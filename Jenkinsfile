pipeline {
    agent any
    tools {
        nodejs 'NodeJS 19.2.0'
    }
    stages {
//        stage('ReactJS App test'){
//            steps {
//                dir('client') {
//                    sh 'ls'
//                    sh 'npm install'
//                    sh 'npm run test --watchAll=false --ci --coverage'
//                }
//
//            }
//        }
        stage('Build client container'){
            agent {
                dockerfile {
                    filename 'Dockerfile.test'
                    dir 'client'
                }
            }
            stages{
                stage(build){
                    steps{
                        sh 'npm'
                    }
                }
            }
        }
    }
}