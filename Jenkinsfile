pipeline {
    
	agent any
	
    stages{
        
        stage('BUILD'){
            steps {
                sh 'mvn clean install package'
                echo 'build complete!'
            }
        }
        stage('Upload to AWS S3') {
              steps {
                withAWS(region:'us-east-1',credentials:'awsS3') {
                    sh 'echo "Uploading content with AWS creds"'
                    s3Upload(file:'/webapp/target/webapp.war', bucket:'practice-maven-artifact-repo', path:'/artifact/')
                  }
            }    
        }

    }
}
