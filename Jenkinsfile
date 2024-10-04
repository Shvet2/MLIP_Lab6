pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
    steps {
        // Activate the virtual environment and run pytest
        echo 'Activating virtual environment...'
        sh '''
            # Switch to bash to use the 'source' command
            bash -c "
                source /home/team07/MLIP_Lab6/mlip/bin
                pytest
                deactivate
            "
        '''
        // Comment this line after implementing pytest
        // exit 1 to ensure the pipeline doesn't exit prematurely
        // exit 1
    }
}

        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our porject'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
