pipeline {
 agent any
 stages{
  stage('Deploy to dev') {
            steps {
                script {
                    namespace = 'dev-v1'
                    deployment = 'samplejava'
                    echo "Deploying application to ${namespace} namespace"
                    withKubeConfig([credentialsId: 'elsegundo-cluster']){
                        //Deleting the old deployment
                        sh ("kubectl delete deployment -n ${namespace} ${deployment}")
                        //Creating new deployment with new image
                        sh ("kubectl apply -f https://raw.githubusercontent.com/kobyshemesh/samplejava/master/deployment.yaml -n ${namespace}")
                        //sh ("kubectl apply -f https://raw.githubusercontent.com/kobyshemesh/samplejava/master/loadbalancer.yaml -n ${namespace}")
                     }
                 
                }
            }
     }
 }
}
