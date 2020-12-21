pipeline {
    agent any

    stages {
        stage('Git checkout') {
            steps {
                checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '**']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/arshiyashafiulla/war-hello-world.git']]]
            }
        }
        stage('Build code') {
            steps {
                echo "code is build"
            }
        }
        stage('zap scan') {
            steps {
                sh '/var/lib/jenkins/tools/com.cloudbees.jenkins.plugins.customtools.CustomTool/ZAP_2.9.0/ZAP_2.9.0/zap.sh -cmd -quickurl http://guru99.com -quickprogress -quickout ~/out1.html'
            }
        }
    }
}
