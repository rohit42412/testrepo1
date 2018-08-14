@Library(commonlib@master) _

node {
  


    stage('Clone sources') {
        git url: 'https://github.com/rohit42412/testrepo1.git'
    }

    stage('Docker Build) {

        sh "cd webapp && docker build PythonWebApp:latest .  "
    }


 stage('Docker Run  App) {
        sh "docker run  --name PythonWebApp:latest -d -p 5000:8000"
    }

    stage ('Run proxy')

    	"sh docker run --name mynginx2 	\
    		-v /etc/nginx.conf:/etc/nginx:ro -P -d nginx
    	"

    stage('Test') {
       sh "curl-vv http://localhost"
    }

   stage('Destory') {
        sh "docker kill --name PythonWebApp:latest "
    }
}