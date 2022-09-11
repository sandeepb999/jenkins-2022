pipeline {
    agent any
        stages {
            stage ('Clone') {
                steps {
                         git branch: 'main', url: 'https://github.com/sandeepb999/jenkins-2022.git'
                      }
            }
            stage ("Build") {
                steps {
                    sh '''
                    pwd
                    cd  Docker/app/maven
                    docker build -t sandeepbobba:1.0 .
                    '''
                }
            }
            stage ("Docker Run" ) {
                steps {
                    sh ''' docker run -it -d -p 8093:8080 sandeepbobba:1.0 '''
                }
            }  
        } 
}
