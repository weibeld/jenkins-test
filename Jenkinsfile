def foo(chartName, chartDir) {
    sh """
        chart_name="$chartName"
        echo "\$chart_name"
    """
}

pipeline {
    agent any
    stages {
        stage('Parallel') {
            parallel {
                stage('Stage 1') {
                    steps {
                        foo("stage1", "/mydir/charts/mychart")
                    }
                }
                stage('Stage 2') {
                    steps {
                        foo("stage2", "/mydir/charts/mychart")
                    }
                }
            }
        }
    }
}
