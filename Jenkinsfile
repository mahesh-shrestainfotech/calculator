pipeline{
    agent any
    stages{
        stage("checkout"){
            steps{
                git url:'https://github.com/mahesh-shrestainfotech/calculator.git'
            }
        }
        
        stage("Compile"){
            steps{
                sh "./gradlew compileJava"
            }
        }
        
        stage("Unit test"){
            steps{
                sh "./gradlew test"
            }
        }
        
        stage("Package"){
        	steps{
        		sh "./gradlew build"
        	}
        }        
        
        stage("Docker build"){
        	steps{
        	    sh "sudo docker login --username mahipatluri --password mahicyrus123"        	
        		sh "sudo docker build -t mahipatluri/calculator ."
        		sh "sudo docker push mahipatluri/calculator"
        	}
        }
        
        
        
    }
}