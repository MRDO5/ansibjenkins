pipeline {
    agent {
	  label 'master'
        }

	triggers {
           pollSCM('* * * * *')
	}

	environment {
		ANSIBLE_CONFIG = "/etc/ansible/ansible.cfg"
		}
        stages{
	    stage('Checkout') {
		steps {
                   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'Jenkins-LTS'], [$class: 'WipeWorkspace']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'fd864bf0-5e33-4cf1-a130-67ac2c22bf17', url: 'https://github.com/MRDO5/jenkins-lts.git']]])
 			}
		}
 	  }
     }


