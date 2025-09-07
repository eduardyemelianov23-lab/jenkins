pipeline {
agent any

parametres {
    string{name: 'BRANCH', defaultValue: 'main', decription: 'Checkout branch'}
}
stages {
    stage('Start') {
        steps {
            echo "=== Start pipeline ==="
        }
    }

    stage('Checkout') {
        steps {
            echo "Checkout to the repo..."
            git url: 'https://github.com/lukaszgolojuch/PlaywrightTests', branch: "$params.BRANCH"
        }
    }

    stage('Test') {
        steps {
            echo "Running tests..."
            bat '.\\gradlew clean test'
        }
    }

    stage('Deploy') {
        steps {
            echo "Deploying application..."
        }
    }
}

post {
    always {
        echo "Pipeline finished."
    }
}
}
