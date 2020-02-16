pipeline {
 stages{
  stage('Deploy to dev') {
    
            steps {
                script {
                    namespace = 'dev-v1'
                    echo "Deploying application to ${namespace} namespace"
                    sh 'kubectl apply -f https://github.com/kobyshemesh/samplejava/blob/master/deployment.yaml -n ${namespace})'
                    sh 'kubectl apply -f https://github.com/kobyshemesh/samplejava/blob/master/loadbalancer.yaml -n ${namespace}'
                }
            }
     }
 }
}
