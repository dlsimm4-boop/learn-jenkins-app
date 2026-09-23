pipeline {
    agent any

    environment {
        NETLIFY_SITE_ID = 'YOUR NETLIFY SITE ID'
        NETLIFY_AUTH_TOKEN = credentials('netlify-token')
        REACT_APP_VERSION = "1.0.$BUILD_ID"
    }

    stages {

        stages('Docker') {
            agent {
          image 'nginx'
                
            }
        steps('BuildDocker'){
            '''
            sh echo "In BuildDocker"
            '''
        }

    
            }
        
    }
}
