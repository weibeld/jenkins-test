def foo(chartName, chartDir) {
    sh """
        chartName="$chartName"
        chartDir="$chartDir"
        chartDir=\${chartDir%/}
        echo "\$chartDir"/Chart.yaml
    """
}

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                foo("mychart", "/mydir/charts/mychart")
                foo("mychart", "/mydir/charts/mychart/")
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
