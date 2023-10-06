pipeline {
    agent any

    stages {
        stage('Check Java') {
            steps {
                script {
                    def javaStatus = sh(script: 'java --version', returnStatus: true)
                    if (javaStatus == 0) {
                        echo 'Java is installed.'
                        currentBuild.result = 'SUCCESS'
                    } else {
                        echo 'Java is not installed.'
                        currentBuild.result = 'FAILURE'
                        error('Java is not installed.')
                    }
                }
            }
        }
 
        stage('Check Maven') {
            steps {
                script {
                    def mavenStatus = sh(script: 'mvn --version', returnStatus: true)
                    if (mavenStatus == 0) {
                        echo 'Maven is installed.'
                        currentBuild.result = 'SUCCESS'
                    } else {
                        echo 'Maven is not installed.'
                        currentBuild.result = 'FAILURE'
                        error('Maven is not installed.')
                    }
                }
            }
        }
 

        stage('Final') {
            steps{
                script {
                    if(currentBuild.result == 'SUCCESS'){
                        echo 'Everything is installed'
                    }else{
                        echo 'Something is not installed'
                    }
                }
            }
        }
    }
}
