pipeline {
    agent any 
    stages {
      
        stage("clone code") {
            steps {
                script {
                    // Let's clone the source
                 git branch: 'main', credentialsId: 'github', url: 'https://github.com/swethark451/project-privateDB'   }
            }
        }
        stage("build") {
            steps { 
                sh "docker build -t flask . "
            }
        }
        
        stage("deploy") {
          steps{
            sh "docker-compose -f docker-compose.yml down && docker-compose -f docker-compose.yml up -d "
          }
        }
      
    }
}

    


