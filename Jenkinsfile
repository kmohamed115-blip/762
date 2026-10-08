pipeline{
    agent{
        label 'docker'
    }
    stages {
        stage('Build Docker image')
        {
            steps{
                script{
                    sh 'docker build -t karim/react -f Dockerfile.dev .'
                }
            }
        }
        stage('Run Tests')
        {
            steps{
                script{
                    env.DOCKER_BUILDKIT = 1
                    sh 'docker run -e CI=true karim/react npm run test'
                }
            }
        }
    }
}