def foo(chartName, chartDir) {
    sh """#!/bin/bash
    echo "\$foo"
    echo "$foo"
    """
}

pipeline {
    agent any
    environment {
        foo = "bar"
    }
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
