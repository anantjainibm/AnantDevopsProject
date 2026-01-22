pipeline {
    agent any

    stages {
        stage('Show Files') {
            steps {
                sh 'ls -la'
                sh 'ls -la cal.games'
            }
        }

        stage('Validate') {
            steps {
                sh '''
                test -f cal.games/index.html
                test -f cal.games/game.js
                echo "✅ CI Passed"
                '''
            }
        }

        stage('Deploy to Nginx') {
            steps {
                sh '''
                sudo rm -rf /var/www/html/*
                sudo cp -r cal.games/* /var/www/html/
                sudo systemctl restart nginx
                echo "✅ Deployed to Nginx"
                '''
            }
        }
    }
}
