pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                echo 'Checkout/Pull Code from Github'
            }
        }
        stage('Compile Code') {
            steps {
                echo 'using Maven Compile the code'
            }
        }
        stage('Run Test Cases') {
            steps {
                echo 'Run Test Cases using Maven'
                sh 'ls'
            }
        }
        stage('Package the Code') {
            steps {
                echo 'Package code using Maven package command'
            }
        }
        stage('Another Stage') {
            steps {
                echo 'Another Stage Added'
            }
        }
    }
}
