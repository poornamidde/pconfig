node {
      stage("Git Clone"){

        git branch: 'main', url: 'https://github.com/chanakyad/Configserver.git'
    }
   
    stage("Docker build"){
    sh 'mvn clean package'
    sh 'docker build -t configserver:latest -f Dockerfile .'
        sh 'docker image ls'
    }
   stage("Deploy"){
    sh ' docker rm -f configserver||true'
    sh 'docker run -d -p 8888:8888 --name configserver configserver:latest '
}
}
