pipeline {
    // See https://www.jenkins.io/doc/tutorials/build-a-java-app-with-maven/
    // The agent block tells Jenkins to run everything inside a docker
    // container that has Maven installed.
    // the args parameter maps the maven repository to a folder on green
    // (the machine running Jenkins)
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}