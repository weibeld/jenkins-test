def foo(chartName, chartDir) {
    sh """
        echo $chartName
        echo $chartDir/Chart.yaml
    """
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
