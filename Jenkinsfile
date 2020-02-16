pipeline {
 agent any
 stages{
  stage('Deploy to dev') {
            steps {
                script {
                    namespace = 'dev-v1'
                    echo "Deploying application to ${namespace} namespace"
                    sh ("kubectl apply -f https://raw.githubusercontent.com/kobyshemesh/samplejava/master/deployment.yaml -n ${namespace}")
                    sh ("kubectl apply -f https://raw.githubusercontent.com/kobyshemesh/samplejava/master/loadbalancer.yaml -n ${namespace}")
                }
            }
     }
 }
}
