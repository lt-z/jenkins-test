pipeline {
    agent none
    tools {
        nodejs '16.15.1'
    }
    stages {
        stage('Build') {
            parallel {
                stage('Build parallel 1') {
                    agent { label 'agent2' }
                    steps {
                        sh 'whereis git' 
                        echo 'Building.. 1'
                        sh 'npm install'
                    }
                }
                stage('Build parallel 2') {
                    agent { label 'agent1' }
                    steps {
                        sh 'whereis git' 
                        echo 'Building.. 2'
                        sh 'npm install'
                    }
                }
            }
        }
        stage('Testing...') {
            parallel {
                stage('Test Parallel 1') {      
                    agent { label 'agent2' }
                    steps {
                        echo 'Testing.. 1'
                        sh 'npm run test'
                    }
                }
                stage('Test Parallel 2') {
                    agent { label 'agent1' }
                    steps {
                        echo 'Testing.. 2'
                        sh 'npm run test'
                    }
                }
            }
        }
    }
}
