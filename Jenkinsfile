pipeline {
		agent any
		// agent { docker { image 'maven:3.6.3' }}
		stages
		{
			stage('Build'){
				steps {
						// sh 'mvn --version'
						echo "PATH - $PATH"
						echo "BUILD NUMBER - $env.BUILD_NUMBER"
						echo "Build ID -$env.Build_ID"
						echo "Build Tag -$env.Build_TAG"
						echo "Build URL -$env.Build_URL"
				}
			}
			stage('Test'){
				steps {
						echo "Test"
				}
			}
			stage('Integration Test'){
				steps {
						echo "Integration Test"
				}
			}
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
