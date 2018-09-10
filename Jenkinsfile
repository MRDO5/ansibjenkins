pipeline {
	agent {
	  label 'master'
        }

	triggers {
           pollSCM('* * * * *')
	}

	environment {
		ANSIBLE_CONFIG = "/etc/ansible/ansible.cfg"

        stages {
	    stage('Checkout') {
		steps {
		   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'jenkins-lts'], [$class: 'WipeWorkspace']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'd7a1c307-48ff-4bdf-b220-96cfffda897d', url: 'git@gitlab.com:mdanielyan/jenkins-lts.git']]])
			}
		}

 	}
    }
}



