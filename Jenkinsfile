pipeline {
        agent any
        stages {
                stage('Build') {
                        steps {
                                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/mhdnurfaizzy/akulaku-test.git']]])
                   }
                }
                stage('Test') {
                        steps {
                                bat 'mvn test -PPurchase.xml'
                        }
                }
        }
}
