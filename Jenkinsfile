pipeline {
	agent any
	tools {
		
	}
	stages {
		stage("build jar") {
			steps{
				script {
					echo "building the application..."
					
				}
			}
		}
		stage("deploy") {
			steps {
				script {
					def dockerCmd = 'docker run -d -p 3080:3080 ofekk/demo-app1'
					sshagent(['ec2-server-key']){
						sh "ssh -o StrictHostKeyChecking=no ec2-user@3.86.12.184 ${dockerCmd}"
					}
					echo "deploying the application..."
				}
			}
		}
	}
}
