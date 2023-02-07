pipeline {
	agent any

	stages {

		stage ('Build Docker Image') {
			steps {
				script {
					dockerapp = docker.build("marod12/kube-news:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
				}
			}
		}

		stage ('Push Docker Image') {
			steps {
				script {
					docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {
						dockerapp.push('latest')
						dockerapp.push("${env.BUILD_ID}")
					}
				}
			}
		}

		stage ('Deploy Kubernetes') {
			environment {
				tag_version = "${env.BUILD_ID}"
			}
			steps { 
				script {
					withKubeConfig([credentialsId:'kubeConfig']) {
						sh 'sed -i "{{TAG}}/$tag_version/g" ./k8s/deployment.yaml'
						sh 'kubectl apply -f ./k8s/deployment.yaml'
					}
				}
			}
		}
	}
}
