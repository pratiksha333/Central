node{

    stage('SCM Checkout')
    {
        git credentialsId: '4cc785e9-441d-4818-a248-2bfb2148004d', url: 'https://github.com/VardhanNS/phpmysql-app.git'
    }
    
    stage('Run Docker Compose File')
    {
        sh 'sudo docker-compose build -S'
        sh 'sudo docker-compose up -d -S'
    }
  stage('PUSH image to Docker Hub')
    {
      /* withCredentials([string(credentialsId: 'DockerHubPassword', variable: '9970036244')]) 
        {
            sh "docker login -u pratiksha26493 -p ${9970036244}"
        }
        sh 'docker push vardhanns/phpmysql_app'
        */
        //docker.withRegistry( 'https://registry.hub.docker.com', 'DockerHubPassword' ) {
             
             sh 'sudo docker login -u "pratiksha26493" -p "Zephyr@17" docker.io'
             //sh 'sudo docker push pratiksha26493/mysql'
             //sh 'sudo docker push pratiksha26493/job1_web1.0'
             sh 'sudo docker push pratiksha26493/job1_web2.0'
            // sh 'docker push pratiksha26493/mysql'
          
    }
}
