pipeline {
    agent {
        label "built-in"
    }
    stages {
        // stage("docker-install") {
        //     steps {
        //         sh ''' 
        //         yum install docker -y
        //         systemctl start docker
        //         docker pull httpd
        //         '''
        //     }
        // }
        stage("git-2025Q3") {
            steps {
                dir("/docker-asign-1/2025Q3/"){
                    git url : "https://github.com/SarthakAJ/docker-repo-1.git",
                    branch : "2025Q3"
                    sh '''
                    docker run -dp 8001:80 --name 2025Q3 httpd
                    docker cp index.html 2025Q3:/usr/local/apache2/htdocs/
                    docker exec 2025Q3 chmod -R 777 /usr/local/apache2/htdocs/
                    '''
                }
            }
        }
    }
}
