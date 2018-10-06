node('php'){
    stage('Clean'){
        deleteDir()
        sh 'ls -la'
    }

    stage('Fetch') {
        checkout scm
    }

    stage('Docker Build') {
        sh 'docker build -t ematos/laravel:$BUILD_NUMBER .'
    }

    stage('Docker Ship') {
        sh 'docker push ematos/laravel:$BUILD_NUMBER'
    }
    
    stage('Docker Clean') {
        sh 'docker rmi -f ematos/laravel:$BUILD_NUMBER'
    }
}
