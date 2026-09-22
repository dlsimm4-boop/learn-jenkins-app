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
                sh 'docker run -d -p 8080:80 --name hello-web nginx:alpine sh -c "echo '<h1>Hello World!</h1>' > /usr/share/nginx/html/index.html && nginx -g 'daemon off;'"
'
            }
        

    
            }
        
    }
}
