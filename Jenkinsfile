pipeline {
	
		agent any
		// agent { docker { image 'maven:3.6.3' }}
		environment {
			dockerHome = tool 'myDocker'
			mavenHome = tool 'myMaven'
			PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
		}
		stages
		{
			stage('Checkout'){
				steps {
						sh 'mvn --version'
						sh 'docker version'
						echo "PATH - $PATH"
						echo "BUILD NUMBER - $env.BUILD_NUMBER"
						echo "Build ID -$env.Build_ID"
						echo "Build Tag -$env.Build_TAG"
						echo "Build URL -$env.Build_URL"
				}
			}
		
			stage('Remote SSH') {
      			sshCommand remote: remote, command: "ls -lrt"
      			sshCommand remote: remote, command: "for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done"
    		}
		
			// stage('Compile'){
			// 	steps{
			// 		sh 'mvn clean compile'
			// 	}
			// }
			// stage('Test'){
			// 	steps {
			// 			sh 'mvn test'
			// 	}
			// }
			// stage('Integration Test'){
			// 	steps {
			// 			sh 'mvn failsafe:integration-test failsafe:verify'
			// 	}
			// }
			// stage('Package'){
			// 	steps {
			// 			sh 'mvn package -DskipTests'
			// 	}
			// }
			// stage('Build Docker Image') {
			// 	steps {
			// 		script{
			// 			// docker build -t swaraj1905/currency-exchange-devops:$env.Build_TAG
			// 			dockerImage = docker.build("swaraj1905/currency-exchange-devops:${env.Build_TAG}")
			// 		}					
			// 	}
			// }
			
			// stage('Push Docker Image') {
			// 	steps {
			// 		script{
			// 			docker.withRegistry('','mydockerhubcred'){
			// 				dockerImage.push();
			// 				dockerImage.push('latest');
			// 			}
						
			// 		}
			// 	}
				
			
		}

		post{
			always{
				echo "I am awesome , I always run"
			}
			success{
				echo "I run on success"
			}
			failure{
				echo "I run on failures"
			}
		}
	}
