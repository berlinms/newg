pipeline {
    agent any

    stages {

        
        stage('clean') {
            steps {
                sh 'gradle clean'
            }
        }
        stage("publish") {
         steps 
          {
           nexusPublisher nexusInstanceId: 'LocalNexus', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'war/target/jenkins.war']], mavenCoordinate: [artifactId: 'jenkins-war', groupId: 'org.jenkins-ci.main', packaging: 'war', version: '2.22']]]
           }

}
}
}

