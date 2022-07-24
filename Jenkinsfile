podTemplate(
        name:'build-pod',
        namespace: 'jenkins',
        podRetention: always(),
        containers: [
            containerTemplate(
                name: 'node14', 
                image: 'node:14-alpine', 
                command: 'sleep', 
                args: '-p 3000:3000 -p 5000:5000'
            )
        ]) {

    node('build-pod') {
        stage('Build') {
            stage('Build 1') {
                sh 'npm install'
            }
        }
    }
}
