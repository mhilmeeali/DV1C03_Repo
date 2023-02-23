pipeline {

    agent any 
    stages {
        
        stage('Stage 1_22051090') {
            steps {
                echo "S1_22051090:Environment Preparation Completed"
            }
        }
        stage('Stage 2_22051090') {
            steps {
                sh "docker rm -f S2_22051090_Server || true"
                sh "docker run -d --name S2_22051090_Server -p 42000:80 22051090_webimage"
                echo "S2_22051090:Web Server Creation Completed"
            }
        }

		stage('Stage 3_22051090 and Stage 4_22051090'){
			parallel{
				stage('API Test'){
					steps{
						echo "S3_22051090:API Test Completed"
					}
				}
				
				stage('DAST Security Test'){
					steps{
						echo "S4_22051090:Dast Security Test Completed"
					}
				}
      }
    }
				    stage('S5_22051090') {
            steps {
				input("Do you want to release the work?")
            }
        }

                           stage('S6_22051090') {
                              when{
				not{
					branch 'master'
				}
			}
			steps {
                echo "Work Released - 22051090"
            }
        }

    }   
}
