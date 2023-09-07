node {
    stage('Clone repository') {
        checkout scm
    }
    stage('Build image') {
        app = docker.build("imkunyoung/flask-example")
    }
    stage('Push image') {
        docker.withRegistry('https://index.docker.io/v1/', 'dockerhub_cred') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
