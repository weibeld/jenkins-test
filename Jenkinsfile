def foo(chartName, chartDir) {
    sh """#!/bin/bash
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
                        foo("stage1", "foo")
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
