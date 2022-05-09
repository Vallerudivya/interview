pipeline {
    agent any

    stages {
        stage('continuous download') {
            steps {
               git 'https://github.com/kliakos/sparkjava-war-example.git' 
            }
        }
         stage('continuous build') {
            steps {
               sh 'mvn install' 
            }
        }
        stage('continuous deployment') {
            steps {
               sh 'sshpass -p "divya"  scp target/sparkjava-hello-world-1.0.war root@172.17.0.4:/var/lib/apache-tomcat-9.0.56/webapps'
            }
        }
    }
}
