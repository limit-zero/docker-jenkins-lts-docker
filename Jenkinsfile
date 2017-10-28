node {
    docker.withRegistry('https://registry.hub.docker.com', 'docker-registry-login') {
        stage('Checkout') {
            checkout scm
        }
        stage('Build') {
            myDocker = docker.build("limit0/jenkins-lts-docker:v${env.BUILD_NUMBER}", '.')
        }
        stage('Push Container') {
            myDocker.push("latest");
            myDocker.push("v${env.BUILD_NUMBER}");
        }
    }
}
