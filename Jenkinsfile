pipeline {
    agent none

    environment {
        CI = 'true'
    }
    
    podTemplate(containers: [
        containerTemplate(
            name: 'node',
            image: 'node:6-alpine',
            command: 'sleep',
            args: '-p 3000:3000 -p 5000:5000',
            namespace: 'jenkins'),
            podRetention: always()
    ]) {

        node(POD_LABEL) {
            stage('Build') {
                container('node') {
                    stage('Build 1') {
                        steps {
                            sh 'npm install && sleep 500'
                        }
                    }
                }
            }
            stage('test') {
                container('node') {
                    stage('test 1') {
                        steps {
                            sh './jenkins/scripts/test.sh && sleep 500'
                        }
                    }
                }
            }
            stage('Test') {
                steps {
                    sh './jenkins/scripts/test.sh'
                }
            }
        }
    }
}
