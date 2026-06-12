pipeline {

agent any

stages {

stage('Clone') {
steps {
git 'https://github.com/<username>/real-estate-project.git'
}
}

stage('Build Image') {
steps {
sh 'docker build -t real-estate-app .'
}
}

stage('Stop Old Containers') {
steps {
sh '''
docker compose down || true
'''
}
}

stage('Deploy') {
steps {
sh '''
docker compose up -d
'''
}
}

}

}
