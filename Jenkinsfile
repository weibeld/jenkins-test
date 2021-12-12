def foo(chartName, chartDir) {
    sh """#!/bin/bash
        chart_name="$chartName"
        echo "\$chart_name"
        sleep 10
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
                        sh 'sleep 5'
                        foo("stage2", "/mydir/charts/mychart")
                    }
                }
            }
        }
    }
}
