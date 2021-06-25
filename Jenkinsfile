pipeline {
  agent any
  stages {
    stage ('Update OS') {
      steps {
        sh 'sudo apt update -y' 
		sh 'sudo apt upgrade -y' 
		sh 'sudo apt autoremove -y' 
		sh 'sudo apt -y install default-jre default-jdk'
      }
    }
    stage ("Install jenkins") {
      steps {
        sh 'sudo apt install jenkins -y'
		sh 'sudo apt upgrade -y'
		sh 'sudo mv /usr/share/jenkins/jenkins.war /usr/share/jenkins/jenkins.war.old'
		sh 'sudo wget https://updates.jenkins-ci.org/latest/jenkins.war'
		sh 'sudo systemctl restart jenkins'
      }
    }
  }
}
