pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[
                            credentialsId: '42835aef-c5fe-4a1d-98cf-9492d71e1298',
                            url: 'https://github.com/hazar1997/CD-devops.git']]])
                }
            }
        }
   	stage('Install') {
             steps{
                script{
                    sh "sudo npm install --force"
                }
            }
        }
stage ('Build') {
	
			steps {
			
			sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
	
			}


	}



	


}
}
