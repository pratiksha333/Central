node{

    stage('SCM Checkout')
    {
        git credentialsId: 'b5adaad4-c434-433b-bbae-da0153425eb8', url: 'https://github.com/pratiksha333/Central.git'
    }
    
    stage('Run Docker Compose File')
    {
        sh 'docker-compose build'
        sh 'docker-compose up -d'
    }
    stage('PUSH image to Docker Hub')
    {
        withCredentials([string(credentialsId: 'DockerHubPassword', variable: 'DHPWD')]) 
        {
            sh "docker login -u pratiksha26493 -p ${DHPWD}"
        }
        sh 'docker push pratiksha26493/php_mysql_app'
    }
}
