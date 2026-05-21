pipeline {
agent any
triggers {
cron('*/2 * * * *')
}
stages {stage('Clone') {
steps {
git 'https://github.com/Prathap023/java-devops-app.git'
}
}
stage('Build Maven') {
steps {
sh 'mvn clean package'
}
}
stage('Build Docker Image') {
steps {
sh 'docker build -t pratap023/dev-repo .'
}
}
stage('Run Container') {
steps {
sh 'docker run -d --name java-container pratap023/dev-repo || true'
}
}
        stage('Output')
        {
          steps{
            sh 'cd src/main/java/com/example'
            sh 'javac App.java'
            sh 'Java App.java'
          }
        }
}
}
