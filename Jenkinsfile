stage('Build') {
    steps {
        dir('jenkins-demo') {
            bat 'mvn clean compile'
        }
    }
}

stage('Test') {
    steps {
        dir('jenkins-demo') {
            bat 'mvn test'
        }
    }
}

stage('Package') {
    steps {
        dir('jenkins-demo') {
            bat 'mvn package'
        }
    }
}