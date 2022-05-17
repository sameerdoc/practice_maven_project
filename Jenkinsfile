pipeline {
    
	agent any
	
    stages{
        
        stage('BUILD'){
            steps {
                sh 'mvn clean install -DskipTests'
                echo 'build complete!'
            }
            
        }


    }


}
