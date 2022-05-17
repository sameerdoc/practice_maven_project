pipeline {
    
	agent any
	
	tools {
        maven "maven3"
        jdk 'jdk8'
    }
	

	
    stages{
        
        stage('BUILD'){
            steps {
                sh 'mvn clean install -DskipTests'
                echo 'build complete!'
            }
            
        }


    }


}
