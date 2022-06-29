pipeline {
    agent any

    environment {
      KNAPSACK_PRO_TEST_SUITE_TOKEN_JEST = "4a0686c9b6e9563f6687b421659d8831"
    }

    stages {
        stage('Build') {
            steps {
              echo 'Building..'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'npm run test'
            }
        }
    }
}
