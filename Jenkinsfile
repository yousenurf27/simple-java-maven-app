node {
    docker.image('maven:3.9.2').inside('-v /root/.m2:/root/.m2') {
        stage('Checkout') {
            checkout scm
        }
        stage('Build') {
            sh 'mvn -B -DskipTests clean package'
        }
    }
}