pipeline {
    agent any

    tools {
        maven "maven"
        jdk "jdk11"
    }

    stages {
        stage('Initialize'){
            steps{
                echo "PATH = ${M2_HOME}/bin:${PATH}"
                echo "M2_HOME = /opt/maven"
            }
        }
/*        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
 */
        stage('Test') {
            steps {
                sh 'ls -la target'
                sh 'rm target/my-app-1.0-SNAPSHOT.jar'
                sh 'pwd'
                sh 'mvn surefire:test'
                sh 'ls -la target'
            
            }
        }
/*         stage('Docker Build') {
            steps {
                script {
                    docker.build("localhost/mvn-app:latest")
                }
            }
        }
        */
     }
}
