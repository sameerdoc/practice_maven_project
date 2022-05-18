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
                dir('/var/lib/jenkins/workspace/maven-build'){
                    withAWS(region:'us-east-1',credentials:'awsS3') {
                        sh 'echo "Uploading content with AWS creds"'
                        s3Upload(bucket:'practice-maven-artifact-repo', workingDir:'/var/lib/jenkins/workspace/maven-build/webapp/target/', includePathPattern:'**/*.war')
                  }
              }
            }    
        }

    }
}
