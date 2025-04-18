pipeline {
    agent any

    environment {
        NETLIFY_AUTH_TOKEN = credentials('NETLIFY_TOKEN')
        SITE_ID = '60590520-ef20-4b86-9090-9b2dde44c21e' // replace with your actual site ID
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Anand-DN/Portfolio.git'
            }
        }

        stage('Deploy to Netlify') {
            steps {
                sh '''
                npm install -g netlify-cli
                netlify deploy --dir=. --prod --site=$SITE_ID --auth=$NETLIFY_AUTH_TOKEN
                '''
            }
        }
    }
}
