#!/usr/bin/env groovy

pipeline {
    agent any
    tools {
        jdk 'java17'
    }
    environment { 
        MODGRADLE_CI = 'true'
    }
    stages {
        stage('Clean') {
            steps {
                dir ('build') {
                    deleteDir()
                }
            }
        }
        // Only one stage, just in case a forge or parchment update releases
        // between stages, which would break stuff.
        stage('Publish') {
            steps {
                echo 'Building'
                sh './gradlew publish'
            }
        }
    }
}