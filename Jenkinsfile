pipeline {
   agent any
   stages {
     stage('Clonar repositorio') {
       steps {
           git branch: 'main', url: 'https://github.com/ivethjulissaeucedaornella-ux/miapp-jenkins.git'
          }
        }
     stage('Construir imagen Docker') {
       steps {
         sh 'docker build -t miapp:latest .'
          }
        }
     stage('Desplegar en Kubernetes') {
       steps {
          sh 'kubectl apply -f deployment.yaml'
          sh 'kubectl apply -f service.yaml'
         }
        }
      }
   }
