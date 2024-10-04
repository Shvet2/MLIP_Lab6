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
        sh '''#!/bin/bash
        echo 'Test Step: Setting up environment and running pytest'

        # Delete the existing virtual environment if present
        if [ -d "./mlip" ]; then
            echo "Removing existing virtual environment..."
            rm -rf ./mlip
        fi

        # Create a new virtual environment
        echo "Creating a new virtual environment..."
        python3 -m venv mlip

        # Activate the virtual environment
        source ./mlip/bin/activate

        # Install dependencies from requirements.txt
        if [ -f "requirements.txt" ]; then
            echo "Installing dependencies from requirements.txt..."
            pip install -r requirements.txt
        else
            echo "requirements.txt not found, skipping dependency installation."
        fi

        # Run pytest in the virtual environment
        pytest --maxfail=1 --disable-warnings -v

        echo 'pytest finished successfully'
        '''
    }
}

        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
