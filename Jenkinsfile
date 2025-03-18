pipeline{

    agent any

    stages{
        stage("Git clone"){
            steps{
                echo "========Clone the code========"
                git url: "https://github.com/Kristof-oe/django_app.git", branch: "main"
            }
        }
        
        stage("Test"){
            steps {
               echo "========Testing========"
               script {
                sh "python3 manage.py test"
               }
            }
        }
        stage("Build"){
            steps {
                echo "========Build the Docker image========"
                sh "docker build -t django_appointment ."
            }
        }
    }
}
   