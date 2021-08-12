#!/usr/bin/env groovy

pipeline {
    agent any
    tools {
        jdk 'java16'
    }
    stages {
        // Only one stage, just in case a forge or parchment update releases
        // between stages, which would break stuff.
        stage('Publish') {
            steps {
                echo 'Building'
                sh './gradlew clean publish'
            }
        }
    }
}