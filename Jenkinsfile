pipeline {
    agent any

    environment {
        // bash is one of the supported shells. Jenkins defaults to sh
        // so we have to set it explicitly here
        SHELL='/bin/bash'
    }

    stages {
        stage ('Environment') {
            steps {
                sh 'env'
            }
        }
        stage ('Install state tool') {
            steps {
                sh'''
                curl -q https://platform.activestate.com/dl/cli/install.sh -o install.sh
                chmod +x install.sh
                ./install.sh -n -t $WORKSPACE || true
                $WORKSPACE/state --version
                '''
            }
        }
        stage ('Run recipe') {
            steps {
                sh '''
                cd ActiveState-Recipes/recipe-577504-compute-mem-footprint
                $WORKSPACE/tool run recipe
                '''
            }
        }
    }
}