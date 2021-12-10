def foo() {
    echo "foo"
}

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    foo()
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
