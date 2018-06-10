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
        	    sh "docker login --username egiantsdocker --password Egaints#1"        	
        		sh "docker build -t mahipatluri/calculator ."
        		sh "docker push mahipatluri/calculator"
        	}
        }
        
        
        
    }
}
