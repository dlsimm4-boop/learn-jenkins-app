pipeline {
    agent any

    environment {
        NETLIFY_SITE_ID = 'YOUR NETLIFY SITE ID'
        NETLIFY_AUTH_TOKEN = credentials('netlify-token')
        REACT_APP_VERSION = "1.0.$BUILD_ID"
    }

    stages {

        stage('Docker') {
            steps {
                //sh 'docker stop web'
                //sh 'docker rm web'
                sh 'docker run --rm -d -p 8180:80 --name web nginx'
                sh 'sleep 60'
            }
        

    
            }
        
    }
}
