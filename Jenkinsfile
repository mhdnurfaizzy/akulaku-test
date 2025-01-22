pipeline {
    agent any
    tools {
        maven 'Maven' // Ensure this matches the name configured in "Global Tool Configuration"
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', 
                          branches: [[name: '*/main']], 
                          userRemoteConfigs: [[url: 'https://github.com/mhdnurfaizzy/akulaku-test.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test -PPurchase' // Ensure Maven is installed and added to the PATH
            }
        }
    }
}
