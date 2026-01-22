pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/anantjainbm/AnantDevopsProject.git'
            }
        }

        stage('Show Project Files') {
            steps {
                sh 'ls -la'
                sh 'ls -la cal.games'
            }
        }

        stage('Basic Validation') {
            steps {
                sh '''
                test -f cal.games/index.html
                test -f cal.games/game.js
                echo "✅ CI Passed: Required files found"
                '''
            }
        }
    }
}
