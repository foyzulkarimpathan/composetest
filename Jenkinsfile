pipeline {
       agent { label 'linux' }
       options {
       buildDiscarder(logRotator(numTokeepstr: '5'))
}
environment {
 DOCKERHUB_CREDENTIALS = credentials('swaccha-dockerhub')
}
stage {
stage('Build') {
steps {
sh './jenkins/build.sh'
}
}
stage('Login') {
steps {
sh './jenkins/login.sh'
}
}
stage('Push') {
steps {
sh './jenkins/push.sh'
}
}
}
post {
always {
sh './jenkins/logout.sh'
}
}
}
