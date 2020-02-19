pipeline {
    agent any

    environment {
        // Bash is one of the supported shells. Jenkins defaults to sh
        // so we have to set it explicitly here
        SHELL="/bin/bash"

        // Since jobs run as the user 'jenkins' we do not have permission
        // to install the state tool anywhere on the current PATH. We 
        // instead update the path here to a known location that we
        // will install to
        PATH="$WORKSPACE:$PATH"
    }

    stages {
        stage ('Environment') {
            steps {
                sh 'env'
            }
        }
        stage ('Install state tool') {
            steps {
                sh'''#!/bin/bash
                     sh <(curl -q https://platform.activestate.com/dl/cli/install.sh -o install.sh) -n -t $WORKSPACE || true
                '''
            }
        }
        stage ('Run recipe') {
            steps {
                sh 'state run recipe'
            }
        }
    }
}