pipeline {
    agent any

    stages {
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
                echo "✅ CI Passed"
                '''
            }
        }
    }
}
