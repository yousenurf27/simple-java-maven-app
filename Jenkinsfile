properties([
    pipelineTriggers([
        pollSCM('H/2 * * * *')
    ])
])

node {
    docker.image('maven:3.9.2').inside('--user root -v /root/.m2:/root/.m2') {
        stage('Build') {
            sh 'mvn -B -DskipTests clean package'
        }
        stage('Test') {
            sh 'mvn test'
        }
    }
}