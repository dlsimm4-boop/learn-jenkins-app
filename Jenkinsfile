pipeline {
    agent any

    environment {
        // Replace with your real site ID (Netlify > Site configuration > Site details)
        NETLIFY_SITE_ID    = '40c0791e-5cdd-49f4-bb2a-ff8d54a23e4e'
        // Must exist in Jenkins as a "Secret text" credential with ID 'netlify-token'
        NETLIFY_AUTH_TOKEN = credentials('nfp_5T5edfBcJGH6qZY5iigRJpCyemvzxqrCf70e')
        REACT_APP_VERSION  = "1.0.$BUILD_ID"
    }

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "Building version $REACT_APP_VERSION"
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la build
                '''
            }
        }

        stage('Deploy') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    npm install netlify-cli
                    node_modules/.bin/netlify --version
                    echo "Deploying to Netlify site $NETLIFY_SITE_ID"
                    node_modules/.bin/netlify deploy --dir=build --prod
                '''
            }
        }
    }
}