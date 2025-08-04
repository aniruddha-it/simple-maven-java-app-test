pipeline{
    agent any
    tools{
    maven ("jenkins-maven")
    }
    stages{
        stage("Checkout"){
            steps{
                echo "========Checkout Git Code========"
                sh 'mvn --version'
               //sh 'git clone https://github.com/jenkins-docs/simple-java-maven-app.git'
            }
        }
        stage("Build"){
            steps{
                echo "========Build========"
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage("Test"){
            steps{
                echo "========Test Code========"
                sh 'mvn test'
            }
        }
        stage("Deliver"){
            steps{
                echo "========Deliver========"
                sh 'java -jar target/*.jar'
            }
        }            
    }
    post{
        always{
            echo "========always========"
        }
        
    } 
}
