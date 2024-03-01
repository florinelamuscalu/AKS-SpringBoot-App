	pipeline {
	    agent any
	    tools {
	        maven 'Maven3'
	    }
	     environment {
	        registryUrl ="acrfloritest.azurecr.io"
	        registryCredential ="ACR"
	        registryname ="docker-spring-boot"
	        dockerImage =""
	    }

	    stages {
	        stage('Checkout') {
	            steps {
	                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/florinelamuscalu/AKS-SpringBoot-App.git']])
	            }
	        }
	        
	        stage ('Build JAR') {
	            steps {
	                sh "mvn clean install"
	            }
	        }
	        
	        stage ('Build image'){
	            steps {
	                script {
	                    dockerImage= docker.build registryName
	                }
	            }
	        }
	        
	         stage('Upload Image to ACR') {
                 steps{   
                     script {
                        docker.withRegistry( "http://${registryUrl}", registryCredential ) {
                        dockerImage.push("$BUILD_NUMBER")
                        }
                    }
                }
            }
            
             stage ('Helm Deploy') {
                  steps {
                    script {
                        sh "helm upgrade ver-$BUILD_NUMBER --install aks-chart --namespace helm-deployment --set image.tag=$BUILD_NUMBER"
                        }
                    }
        }

	    }
}
