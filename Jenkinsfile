podTemplate(
        name:'build-pod',
        namespace: 'jenkins',
        podRetention: always(),
        containers: [
            containerTemplate(
                name: 'golang', 
                image: 'golang:1.16.5', 
                command: 'sleep', 
                args: '99d'
            )
        ]) {

    node('build-pod') {
        stage('Build') {
            stage('Build 1') {
                sh 'ls -l'
            }
        }
    }
}
