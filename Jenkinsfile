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
        
        
    }
}