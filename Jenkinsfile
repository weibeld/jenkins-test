def foo(chartName, chartDir) {
    echo "foo"
}

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                foo("mychart", "/mydir/charts/mychart")
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
