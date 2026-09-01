pipeline {
agent any

```
environment {
    DEPLOY_DIR = 'C:\\Users\\Krushnali\\Desktop\\finalyear\\devoops\\Exp_6'
}

stages {

    stage('Checkout') {
        steps {
            echo 'Checking out source code from GitHub...'

            git branch: 'main',
                url: 'https://github.com/krushh67/EXP_6_CI-CD.git'
        }
    }

    stage('Build') {
        steps {
            echo 'Build started...'
            bat 'dir'
            echo 'Build completed successfully!'
        }
    }

    stage('Test') {
        steps {
            echo 'Testing HTML files...'

            bat '''
            if exist index.html (
                echo index.html found successfully!
            ) else (
                echo ERROR: index.html not found!
                exit /b 1
            )
            '''

            echo 'Test completed successfully!'
        }
    }

    stage('Deploy') {
        steps {
            echo 'Deploying web application...'

            bat '''
            if not exist "%DEPLOY_DIR%" mkdir "%DEPLOY_DIR%"

            copy /Y index.html "%DEPLOY_DIR%\\"
            copy /Y style.css "%DEPLOY_DIR%\\"
            copy /Y script.js "%DEPLOY_DIR%\\"
            '''

            echo 'Deployment completed successfully!'
        }
    }
}

post {
    success {
        echo 'Pipeline finished successfully!'
        echo 'Application deployed successfully!'
    }

    failure {
        echo 'Pipeline failed! Check console logs.'
    }
}
```

}
