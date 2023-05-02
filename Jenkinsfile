node {
    def app

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build('flaviopepino/example-app')
    }

    stage('Push image'){
        docker.withRegistry('https://registry.hub.docker.com','docker-hun-credentials') {
            app.push('latest')
        }
    }

}