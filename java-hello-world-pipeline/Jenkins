pipeline {
    agent {
        docker { image 'openjdk:17-alpine' }
    }
    stages {
        stage('Create Java File') {
            steps {
                sh '''
                cat <<EOF > Hello.java
                public class Hello {
                    public static void main(String[] args) {
                        System.out.println("Hello from Jenkins Pipeline!");
                    }
                }
                EOF
                '''
            }
        }
        stage('Compile') {
            steps {
                sh 'javac Hello.java'
            }
        }
        stage('Run') {
            steps {
                sh 'java Hello'
            }
        }
    }
}
