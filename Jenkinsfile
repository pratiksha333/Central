node{

    stage('SCM Checkout')
    {
        git credentialsId: 'a0e1561d-6bf5-48be-ac3c-f547c1bfd0b4', url: 'https://github.com/pratiksha333/Central.git'
    }
    
    stage('Run Docker Compose File')
    {
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
