pipeline {
    
	agent any
	
    stages{
        
        stage('BUILD'){
            steps {
                sh 'mvn clean install package'
                echo 'build complete!'
            }
            
        }


    }


}
