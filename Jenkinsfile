pipeline{
    agent any

    stages{
        stage('zip the file'){
            steps{
                sh 'zip ansible-${BUILD_ID}.zip * --exclude Jenkinsfile'
            }
        }
        stage('upload artifacts to jfrog'){
            steps{
                sh 'curl -uadmin:AP5hovDc2p15yy6qPUt69bTZWL3 -T \
                ansible-${BUILD_ID}.zip "http://18.209.179.74:8081/artifactory/ansible/ansible-${BUILD_ID}.zip"'
            }
        }
    }
}