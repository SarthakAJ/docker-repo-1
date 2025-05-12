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
        stage("git-2025Q1") {
            steps {
                dir("/docker-asign-1/2025Q1/"){
                    git url : "https://github.com/SarthakAJ/docker-repo-1.git",
                    branch : "2025Q1"
                    sh '''
                    docker run -dp 80:80 --name 2025Q1 httpd
                    docker cp index.html 2025Q1:/usr/local/apache2/htdocs/
                    docker exec 2025Q1 chmod -R 777 /usr/local/apache2/htdocs/
                    '''
                }
            }
        }
    }
}
