pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    agent any
        
    
    stages {
        stage('build and push') {
            when {
                branch 'master'
            }
            sh "docker build -t rashtecq/getting-started ."

            steps {
                withDockerRegistry([url: "", credentialsId: "dockerbuildbot-index.docker.io"]) {
                    sh("docker push rashtecq/getting-started")
                }
            }
        }
    }
}
