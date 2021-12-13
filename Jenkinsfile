def foo(chartName, chartDir=null) {
    sh """#!/bin/bash
    chart_name="$chartName"
    chart_dir="$chartDir"
    echo "$chartName"
    echo "$chartDir"
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
                        foo("stage1")
                    }
                }
                stage('Stage 2') {
                    steps {
                        foo("stage2", "foo")
                    }
                }
            }
        }
    }
}
