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
		   checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[ credentialsId: gitlab-token,  url: 'git@gitlab.com:mdanielyan/jenkins-lts.git']]])

			}
		}
 	}
    }




