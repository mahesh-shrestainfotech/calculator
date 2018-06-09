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
        
        stage("Docker login") {
      		steps {
        		withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'leszko',
                          usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
          		sh "docker login --username $USERNAME --password $PASSWORD"
        	}
      		}
    	}
        
        
        stage("Docker build"){
        	steps{
        	    sh "docker login --username mahipatluri --password mahicyrus123"        	
        		sh "docker build -t mahipatluri/calculator ."
        		sh "docker push mahipatluri/calculator"
        	}
        }
        
        
        
    }
}